<template>
  <div>
    <v-row class="contact-content mx-0">
      <v-col
        align-self="center"
        cols="12"
        md="6"
        sm="12"
        class="col-height d-flex flex-column justify-md-space-between pa-sm-0"
      >
        <h1 class="h1-color mb-4">Kontakta mig</h1>
        <template>
          <v-form class="contact-form d-flex flex-column justify-space-between">
            <div>
              <v-row>
                <v-col cols="12" md="6" sm="6">
                  <v-text-field
                    v-model="firstName"
                    :error-messages="firstNameErrors"
                    :counter="10"
                    label="Förnamn"
                    required
                    solo
                    @input="$v.firstName.$touch()"
                    @blur="$v.firstName.$touch()"
                  ></v-text-field>
                </v-col>
                <v-col cols="12" md="6" sm="6">
                  <v-text-field
                    v-model="lastName"
                    :error-messages="lastNameErrors"
                    :counter="10"
                    label="Efternamn"
                    required
                    solo
                    @input="$v.lastName.$touch()"
                    @blur="$v.lastName.$touch()"
                  ></v-text-field>
                </v-col>
              </v-row>
              <v-text-field
                v-model="email"
                class="email-input"
                :error-messages="emailErrors"
                label="E-post"
                required
                solo
                @input="$v.email.$touch()"
                @blur="$v.email.$touch()"
              ></v-text-field>
              <v-textarea
                v-model="message"
                class="text-area"
                :error-messages="messageErrors"
                :rules="rules"
                label="Meddelande"
                required
                counter
                solo
                @change="$v.message.$touch()"
                @blur="$v.message.$touch()"
              ></v-textarea>
            </div>
            <div class="form-buttons">
              <v-btn class="mr-4" color="teal" x-large rounded @click="submit"
                >Skicka</v-btn
              >
              <v-btn x-large rounded @click="clear">Rensa</v-btn>
              <!-- color="#2EC4B6" -->
              <!-- color="#3CDBD3" -->
              <!-- color="#34E4EA" -->
              <!-- color="#72E1D1" -->
              <!-- color="#4CB5AE" -->
              <!-- color="#B2DDF7" -->
              <!-- color="#81D6E3" -->
              <!-- color="#4CB5AE" -->
              <!-- color="#68B0AB" -->
              <!-- color="#00C49A" -->
            </div>
            <!-- Submit status -->
            <div class="py-5 px-12 d-flex justify-center">
              <div v-if="submitStatus === 'PENDING'" class="white--text">
                Skickar...
              </div>
              <div v-if="submitStatus === 'OK'" class="white--text">
                E-post skickat!
              </div>
              <div v-if="submitStatus === 'FORMERROR'" class="error-text">
                Var god och fyll i formuläret korrekt.
              </div>
              <div v-if="submitStatus === 'POSTERROR'" class="error-text">
                Något gick fel! Försök igen.
              </div>
            </div>
          </v-form>
        </template>
      </v-col>
      <v-col align-self="center" class="col-height">
        <div class="map-container">
          <div id="map"></div>
        </div>
      </v-col>
    </v-row>
    <v-row class="d-flex align-center justify-center social-content mx-0">
      <div class="d-flex flex-column pa-sm-16">
        <h2 class="text-center">Kontakt uppgifter</h2>
        <a href="mailto:valesca.sarrocchi.s@gmail.com"
          ><v-icon>mdi-email</v-icon>valesca.sarrocchi.s@gmail.com</a
        >
        <a href="https://github.com/vsarrocchi" target="_blank"
          ><v-icon>mdi-github</v-icon>https://github.com/vsarrocchi</a
        >
        <a href="https://linkedin.com/in/valesca-sarrocchi" target="_blank"
          ><v-icon>mdi-linkedin</v-icon
          >https://linkedin.com/in/valesca-sarrocchi</a
        >
      </div>
    </v-row>
  </div>
</template>

<script>
import { Loader } from '@googlemaps/js-api-loader'
import { validationMixin } from 'vuelidate'
import { required, maxLength, email } from 'vuelidate/lib/validators'
import axios from 'axios'

export default {
  mixins: [validationMixin],
  validations: {
    firstName: { required, maxLength: maxLength(10) },
    lastName: { required, maxLength: maxLength(10) },
    email: { required, email },
    message: { required },
  },
  data: () => ({
    firstName: '',
    lastName: '',
    email: '',
    message: '',
    submitStatus: null,
    rules: [(v) => v.length <= 700 || 'Max 700 characters'],
  }),
  computed: {
    firstNameErrors() {
      const errors = []
      if (!this.$v.firstName.$dirty) return errors
      !this.$v.firstName.maxLength &&
        errors.push('Name must be at most 10 characters long')
      !this.$v.firstName.required && errors.push('Name is required.')
      return errors
    },
    lastNameErrors() {
      const errors = []
      if (!this.$v.lastName.$dirty) return errors
      !this.$v.lastName.maxLength &&
        errors.push('Name must be at most 10 characters long')
      !this.$v.lastName.required && errors.push('Name is required.')
      return errors
    },
    emailErrors() {
      const errors = []
      if (!this.$v.email.$dirty) return errors
      !this.$v.email.email && errors.push('Must be valid e-mail')
      !this.$v.email.required && errors.push('E-mail is required')
      return errors
    },
    messageErrors() {
      const errors = []
      if (!this.$v.message.$dirty) return errors
      !this.$v.message.required && errors.push('Item is required')
      return errors
    },
  },
  mounted() {
    // Google maps API
    const loader = new Loader({
      apiKey: process.env.NUXT_GOOGLE_MAPS_API_KEY,
      version: 'weekly',
    })
    let map
    loader.load().then(() => {
      // eslint-disable-next-line no-undef
      map = new google.maps.Map(document.getElementById('map'), {
        center: { lat: 59.334591, lng: 18.06324 },
        zoom: 12,
        styles: [
          {
            elementType: 'geometry',
            stylers: [
              {
                color: '#171b21',
              },
            ],
          },
          {
            elementType: 'labels.text.stroke',
            stylers: [
              {
                color: '#242f3e',
              },
            ],
          },
          {
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#ffffff',
              },
            ],
          },
          {
            featureType: 'administrative.locality',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#ffffff',
              },
            ],
          },
          {
            featureType: 'poi',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#ffffff',
              },
            ],
          },
          {
            featureType: 'poi.park',
            elementType: 'geometry',
            stylers: [
              {
                color: '#263c3f',
              },
            ],
          },
          {
            featureType: 'poi.park',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#ffffff',
              },
            ],
          },
          {
            featureType: 'road',
            elementType: 'geometry',
            stylers: [
              {
                color: '#38414e',
              },
            ],
          },
          {
            featureType: 'road', // calles
            elementType: 'geometry.stroke',
            stylers: [
              {
                color: '#212a37',
              },
            ],
          },
          {
            featureType: 'road',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#9ca5b3',
              },
            ],
          },
          {
            featureType: 'road.highway',
            elementType: 'geometry',
            stylers: [
              {
                color: '#746855', // calles
              },
            ],
          },
          {
            featureType: 'road.highway',
            elementType: 'geometry.stroke',
            stylers: [
              {
                color: '#171b21',
              },
            ],
          },
          {
            featureType: 'road.highway',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#f3d19c',
              },
            ],
          },
          {
            featureType: 'transit',
            elementType: 'geometry',
            stylers: [
              {
                color: '#2f3948', // transit
              },
            ],
          },
          {
            featureType: 'transit.station',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#d59563',
              },
            ],
          },
          {
            featureType: 'water',
            elementType: 'geometry',
            stylers: [
              {
                color: '#d0a77f', // agua
              },
            ],
          },
          {
            featureType: 'water',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#d0a77f',
              },
            ],
          },
          {
            featureType: 'water',
            elementType: 'labels.text.stroke',
            stylers: [
              {
                color: '#d0a77f',
              },
            ],
          },
        ],
      })
      // eslint-disable-next-line no-console
      console.log(map)
    })
  },
  methods: {
    submit(e) {
      e.preventDefault()
      this.$v.$touch()

      const obj = {
        firstName: this.firstName,
        lastName: this.lastName,
        fromEmail: this.email,
        message: this.message,
      }
      if (
        obj.firstName !== '' &&
        this.$v.firstName.$error !== true &&
        obj.lastName !== '' &&
        this.$v.lastName.$error !== true &&
        obj.fromEmail !== '' &&
        this.$v.email.$error !== true &&
        obj.message !== '' &&
        this.$v.message.$error !== true
      ) {
        axios
          .post('/.netlify/functions/contact-mail', {
            firstname: obj.firstName,
            lastname: obj.lastName,
            email: obj.fromEmail,
            message: obj.message,
          })
          .then(() => {
            this.submitStatus = 'PENDING'
            setTimeout(() => {
              this.submitStatus = 'OK'
            }, 1000)
            this.clear()
          })
          .catch(() => {
            this.submitStatus = 'POSTERROR'
          })
      } else {
        this.submitStatus = 'FORMERROR'
      }
    },
    clear() {
      this.$v.$reset()
      this.firstName = ''
      this.lastName = ''
      this.email = ''
      this.message = ''
      this.submitStatus = null
    },
  },
  head: {
    title: 'Kontakt - Valesca Sarrocchi',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Kontakt - Valesca Sarrocchi',
      },
    ],
  },
}
</script>

<style lang="scss">
.contact-content {
  min-height: 100vh;
  background-color: #171b21;
  padding-top: 56px;
}

.h1-color {
  color: #d0a77f;
}

.contact-form {
  padding-bottom: 20px;
}

.email-input {
  padding: 12px 0 !important;
}

.text-area {
  padding-top: 12px !important;
}

.map-container {
  height: 50vh;
  padding: 2rem 0 0 0 !important;
  #map {
    height: 100%;
    border-radius: 5px;
  }
}

.theme--light.v-counter {
  color: white !important;
}

.social-content {
  background-color: #171b21;
  padding: 6rem 0 8rem 0;
  div {
    border: 2px solid #d0a77f;
    border-radius: 5px;
    color: #d0a77f !important;
    font-weight: bold;
    width: 90%;
    h2 {
      background-color: #171b21;
      width: 16rem;
      margin: auto;
      font-size: 2rem !important;
    }
    a {
      color: #d0a77f;
      display: flex;
      padding: 8px;
      text-decoration: none;
      .v-icon {
        color: #d0a77f;
        margin-right: 7px;
        font-size: 1.8rem;
      }
    }
  }
}

.error-text {
  color: #ff5252;
}

@media (min-width: 600px) and (max-width: 767px) {
  .contact-content {
    padding: 56px 5%;
  }
  .contact-form {
    padding: 10px 0 5rem 0;
    height: 80%;
  }
  .social-content {
    padding: 1rem 0 8rem 0;
    div {
      width: unset;
    }
  }
}

@media (min-width: 768px) {
  .contact-content {
    padding: 56px 10% 0 10%;
  }
  .contact-form {
    // padding: 10px 0 5rem 0;
    height: 450px;
  }
  .map-container {
    height: 510px;
    padding-top: 5rem !important;
  }
  .social-content {
    // padding: 1rem 0 8rem 0;
    div {
      width: unset;
      h2 {
        transform: translateY(-90px);
      }
      a {
        transform: translateY(-20px);
        font-size: 1.2rem;
      }
    }
  }
}

@media (min-width: 960px) {
  .contact-form {
    padding-right: 10%;
  }
  .social-content {
    padding: 1rem 0 8rem 0;
  }
  .map-container {
    padding: 0 !important;
  }
}

@media (width: 653px) and (height: 280px) {
  .map-container {
    height: 90vh;
  }
}

@media (width: 640px) and (height: 360px) {
  .contact-form {
    padding: 10px 0 0 0;
  }
  .map-container {
    height: 90vh !important;
    padding: 0 !important;
  }
}
@media (width: 640px) and (height: 384px) {
  .contact-form {
    padding: 10px 0 0 0;
  }
  .map-container {
    height: 90vh !important;
    padding: 0 !important;
  }
}

@media (width: 1024px) and (height: 600px) {
  .contact-content {
    padding: 56px 10%;
  }
}

@media (width: 280px) and (height: 653px) {
  .social-content div {
    width: 100%;
  }
  .social-content div a {
    font-size: unset;
  }
}

@media (width: 768px) and (height: 1024px) {
  .map-container {
    margin-top: 4rem;
  }
}

@media (width: 1024px) and (height: 1366px) {
  .col-height {
    min-height: unset;
  }
  .map-container {
    height: 40vh;
  }
}
</style>
