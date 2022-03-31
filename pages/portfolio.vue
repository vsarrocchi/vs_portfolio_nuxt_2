<template>
  <div>
    <v-row class="portfolio-content mx-0">
      <v-col
        align-self="center"
        class="col-height d-flex flex-column justify-space-between"
      >
        <h1>Portfolio</h1>
        <p class="portfolio-start-text">
          Välkommen till min portfolio. Här visas några av de projekt och
          tekniker som jag jobbade med under utbildningen, praktiken och arbete
          som Frontend utvecklare.
        </p>
        <PortfolioItems />
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  head: {
    title: 'Portfolio - Valesca Sarrocchi',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Portfolio - Valesca Sarrocchi',
      },
    ],
  },
}
</script>

<style lang="scss">
.portfolio-content {
  min-height: 100vh;
  background-color: #171b21;
  color: #d0a77f;
  padding-top: 56px;
  .portfolio-start-text {
    font-size: 1.5rem;
    padding: 1rem 0;
  }
}

@media (min-width: 768px) {
  .portfolio-content {
    padding: 56px 10%;
  }
}

@media (min-width: 960px) {
  .portfolio-content {
    padding: 15vh 10%;
  }
}
</style>
