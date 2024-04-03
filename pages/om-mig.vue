<template>
  <div>
    <v-row class="om-mig-content mx-0">
      <v-col
        align-self="center"
        cols="12"
        md="6"
        sm="12"
        class="col-height d-flex flex-column justify-space-between om-mig-col1"
      >
        <h1>Om mig</h1>
        <p class="om-mig-text py-4">
          <!-- Hej! Mitt namn är Valesca och jag är en junior Frontend utvecklare
          bosatt i Stockholm. Jag tog examen i maj 2020 i Nackademin och har
          drygt ett års arbetserfarenhet som Frontend utvecklare. -->
          Jag är en praktisk och strukturerad Frontend-utvecklare baserad i
          Stockholm med över tre års erfarenhet inom branschen.
        </p>
        <p class="om-mig-text py-4">
          <!-- Mitt mål är att hitta en plats där jag kan fortsätta att förbättra
          mina färdigheter som utvecklare, samtidigt som jag känner mig genuint
          motiverad att arbeta tillsammans med mina kollegor och med de projekt
          jag är tilldelad. -->
          Mitt mål är att fortsätta utveckla mina färdigheter och bidra till
          spännande projekt. Jag är en person som trivs med utmaningar och
          problemlösning, och oavsett uppdrag tar jag det på allvar och utför
          det med noggrannhet och engagemang.
        </p>
        <NuxtLink to="/kontakt" class="text-decoration-none mx-auto om-mig-btn">
          <v-btn x-large elevation="6" color="#d0a77f" rounded
            >Kontakta mig</v-btn
          >
        </NuxtLink>
      </v-col>
      <v-col
        align-self="center"
        cols="12"
        md="6"
        sm="12"
        class="col-height d-flex align-center"
      >
        <img
          :src="require('../assets/images/profilbild.png')"
          width="100%"
          alt="Valesca Sarrocchi"
        />
      </v-col>
    </v-row>
    <v-row class="om-mig-content mx-0">
      <v-col class="pa-0">
        <h2 class="om-mig-h2 pb-12 text-center">Relevant erfarenhet</h2>
        <TimeLine />
      </v-col>
    </v-row>
    <v-row class="om-mig-content text-center mx-0">
      <v-col class="pa-0">
        <Skills />
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  head: {
    title: 'Om mig - Valesca Sarrocchi',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Om mig - Valesca Sarrocchi',
      },
    ],
  },
}
</script>

<style lang="scss">
h2 {
  color: #171b21;
  font-size: 3rem !important;
}

.om-mig-content {
  color: #171b21;
  min-height: 100vh;
  font-size: 1.5rem;
  padding-top: 56px;
}

.om-mig-col1 {
  padding-bottom: 3rem;
}

.om-mig-text {
  font-size: 1.3rem;
}

@media (min-width: 768px) {
  .om-mig-content {
    padding: 0 10%;
    padding-top: 56px;
  }
  .om-mig-text {
    letter-spacing: 0.05em;
    line-height: 1.8em;
    padding: 0 10% 0 0;
  }
}
</style>
