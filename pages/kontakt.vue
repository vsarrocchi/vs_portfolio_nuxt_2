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
        <KontaktForm />
      </v-col>
      <v-col align-self="center" class="col-height">
        <GoogleMap />
      </v-col>
    </v-row>
    <ContactLinks />
  </div>
</template>

<script>
export default {
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

label {
  color: white;
}

.theme--light.v-counter {
  color: white !important;
}

.error-text {
  color: #ff5252;
}

@media (min-width: 600px) and (max-width: 767px) {
  .contact-content {
    padding: 56px 5%;
  }
}

@media (min-width: 768px) {
  .contact-content {
    padding: 56px 10% 0 10%;
  }
}

@media (width: 1024px) and (height: 600px) {
  .contact-content {
    padding: 56px 10%;
  }
}

@media (width: 1024px) and (height: 1366px) {
  .col-height {
    min-height: unset;
  }
}
</style>
