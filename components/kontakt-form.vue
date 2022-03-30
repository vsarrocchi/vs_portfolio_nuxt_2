<template>
  <v-form class="contact-form d-flex flex-column justify-space-between">
    <div>
      <v-row>
        <v-col cols="12" md="6" sm="6" class="pb-0">
          <label for="firstname">Förnamn</label>
          <v-text-field
            id="firstname"
            v-model="firstName"
            :error-messages="firstNameErrors"
            :counter="10"
            required
            solo
            @input="$v.firstName.$touch()"
            @blur="$v.firstName.$touch()"
          ></v-text-field>
        </v-col>
        <v-col cols="12" md="6" sm="6" class="pb-0">
          <label for="lastname">Efternamn</label>
          <v-text-field
            id="lastname"
            v-model="lastName"
            :error-messages="lastNameErrors"
            :counter="10"
            required
            solo
            @input="$v.lastName.$touch()"
            @blur="$v.lastName.$touch()"
          ></v-text-field>
        </v-col>
      </v-row>
      <v-row>
        <v-col class="pb-0 pt-0">
          <label for="email">E-post</label>
          <v-text-field
            id="email"
            v-model="email"
            :error-messages="emailErrors"
            required
            solo
            @input="$v.email.$touch()"
            @blur="$v.email.$touch()"
          ></v-text-field>
        </v-col>
      </v-row>
      <v-row>
        <v-col class="pt-0">
          <label for="message">Meddelande</label>
          <v-textarea
            id="message"
            v-model="message"
            :error-messages="messageErrors"
            :rules="rules"
            required
            counter
            solo
            @change="$v.message.$touch()"
            @blur="$v.message.$touch()"
          ></v-textarea>
        </v-col>
      </v-row>
    </div>
    <div class="form-buttons">
      <v-btn class="mr-4" color="#3CDBD3" x-large rounded @click="submit"
        >Skicka</v-btn
      >
      <v-btn x-large rounded @click="clear">Rensa</v-btn>
    </div>
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
<script>
import { validationMixin } from 'vuelidate'
import { required, maxLength, email } from 'vuelidate/lib/validators'
import axios from 'axios'

export default {
  mixins: [validationMixin],
  validations: {
    firstName: { required, maxLength: maxLength(30) },
    lastName: { required, maxLength: maxLength(50) },
    email: { required, email },
    message: { required },
  },
  data: () => ({
    firstName: '',
    lastName: '',
    email: '',
    message: '',
    submitStatus: null,
    rules: [(v) => v.length <= 2000 || 'Max 2000 characters'],
  }),
  computed: {
    firstNameErrors() {
      const errors = []
      if (!this.$v.firstName.$dirty) return errors
      !this.$v.firstName.maxLength &&
        errors.push('Förnamn får max vara 30 bokstäver långt')
      !this.$v.firstName.required && errors.push('Förnamn är obligatorisk.')
      return errors
    },
    lastNameErrors() {
      const errors = []
      if (!this.$v.lastName.$dirty) return errors
      !this.$v.lastName.maxLength &&
        errors.push('Efternamn får max vara 50 bokstäver långt')
      !this.$v.lastName.required && errors.push('Efternamn är obligatorisk.')
      return errors
    },
    emailErrors() {
      const errors = []
      if (!this.$v.email.$dirty) return errors
      !this.$v.email.email && errors.push('Ange en giltig emailadress')
      !this.$v.email.required && errors.push('E-post är obligatorisk.')
      return errors
    },
    messageErrors() {
      const errors = []
      if (!this.$v.message.$dirty) return errors
      !this.$v.message.required && errors.push('Meddelandet är obligatorisk.')
      return errors
    },
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
}
</script>
<style lang="scss">
label {
  color: white;
}

.contact-form {
  padding-bottom: 20px;
}

.theme--light.v-counter {
  color: white !important;
}

.error-text {
  color: #ff5252;
}

@media (min-width: 600px) and (max-width: 767px) {
  .contact-form {
    padding: 10px 0 5rem 0;
    height: 80%;
  }
}

@media (min-width: 768px) {
  .contact-form {
    height: 450px;
  }
}

@media (min-width: 960px) {
  .contact-form {
    padding-right: 10%;
  }
}

@media (width: 640px) and (height: 360px) {
  .contact-form {
    padding: 10px 0 0 0;
  }
}
@media (width: 640px) and (height: 384px) {
  .contact-form {
    padding: 10px 0 0 0;
  }
}
</style>
