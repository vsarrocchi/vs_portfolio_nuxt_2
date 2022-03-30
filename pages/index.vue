<template>
  <v-col
    class="background-image d-flex flex-column justify-center align-center"
  >
    <h1 class="d-flex heading-1 my-2"><NameSvg /></h1>
    <h2 class="heading-2 my-2">Frontend Developer</h2>
    <NuxtLink to="/kontakt" class="text-decoration-none">
      <v-btn class="my-8" x-large elevation="6" color="#d0a77f" rounded
        >Kontakta mig</v-btn
      >
    </NuxtLink>
  </v-col>
</template>

<script>
export default {
  head: {
    title: 'Hem - Valesca Sarrocchi',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Hem - Valesca Sarrocchi',
      },
    ],
  },
}
</script>
<style lang="scss">
.background-image {
  background-image: url('../assets/images/artem-sapegin-180146-unsplash-2.jpg');
  background-size: cover;
  height: 100vh;
  background-position: center bottom;
  background-repeat: no-repeat;
}

.heading-1 {
  width: 100%;
}

.heading-2 {
  letter-spacing: 0.2em;
  text-align: center;
}
</style>
