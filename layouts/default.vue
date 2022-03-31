<template>
  <v-app>
    <Navigation />
    <v-main class="min-height-width-100">
      <v-container class="min-height-width-100 pa-0">
        <nuxt class="min-height-width-100" />
      </v-container>
    </v-main>
    <v-footer class="d-flex justify-center footer-content">
      <span>Skapad av Valesca Sarrocchi</span>
    </v-footer>
    <Social />
  </v-app>
</template>

<script>
import Social from '../components/social'
import Navigation from './navigation'

export default {
  components: {
    Social,
    Navigation,
  },
}
</script>

<style lang="scss">
*,
*:before,
*:after {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
  height: 100%;
}

body {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}

.min-height-width-100 {
  min-height: 100vh;
  min-width: 100vw;
}

h1 {
  font-size: 3.5rem;
}

.footer-content {
  background-color: #171b21 !important;
  color: #d0a77f !important;
  font-weight: bold;
}

.v-list-item__title {
  color: #d0a77f !important;
}

@media (min-width: 640px) {
  /* ... */
}

@media (min-width: 768px) {
  .main-content {
    max-width: 1200px;
    margin: 70px auto;
    padding: 0 4.7rem;
  }
}

@media (min-width: 1024px) {
  /* ... */
}

@media (min-width: 1280px) {
  /* ... */
}
</style>
