<template>
  <v-timeline>
    <v-timeline-item
      v-for="(experience, i) in experiences"
      :key="i"
      :color="experience.color"
      small
    >
      <template v-slot:opposite>
        <span
          :class="`headline font-weight-bold beige-color`"
          v-text="experience.title"
        ></span>
      </template>
      <div class="py-4">
        <h2
          :class="`headline ${i % 2 !== 0 ? 'even' : ''}`"
          v-text="experience.company"
        ></h2>
        <div
          :class="[
            i % 2 !== 0
              ? 'even font-weight-light subtitle-1'
              : 'font-weight-light subtitle-1',
          ]"
          v-text="experience.year"
        ></div>
        <p
          :class="[
            i % 2 !== 0
              ? 'even font-weight-light body-1'
              : 'font-weight-light body-1',
          ]"
          v-text="experience.description"
        ></p>
      </div>
    </v-timeline-item>
  </v-timeline>
</template>

<script>
export default {
  data: () => ({
    experiences: [
      {
        color: '#d0a77f',
        year: 'Mars 2021 - Februari 2022',
        title: 'Junior Frontend utvecklare',
        company: 'Cinode',
        description:
          'Arbetade heltid med att skapa anpassade CV mallar och med utveckla företagets applikation. Teknologier som användes under den här perioden inkluderar bland annat: Angular, TypeScript, Sass och C#.',
      },
      {
        color: '#d0a77f',
        year: 'Juli 2020 - oktober 2020',
        title: 'Junior Frontend utvecklare',
        company: 'WCAG Networks',
        description:
          'Arbetade deltid med att göra tillgänglighets analyser av digitala gränssnitt gentemot WCAG riktlinjerna.',
      },
      {
        color: '#d0a77f',
        year: 'Mars 2018 - Maj 2020',
        title: 'Frontend utvecklare',
        company: 'Nackademin',
        description: 'Yrkesutbildning',
      },
      {
        color: '#d0a77f',
        year: 'Januari 2020 - Maj 2020',
        title: 'LIA 2 - Frontend utvecklare',
        company: 'B3 Consulting Group',
        description:
          'Teknologier som användes under praktiken inkluderar bland annat: Vue, Nuxt, Vuex Store, Axios, Vuetify, Vuelidate och Contentful.',
      },
      {
        color: '#d0a77f',
        year: 'September 2019 - December 2019',
        title: 'LIA 1 - Frontend utvecklare',
        company: 'EMG - Education Media Group',
        description:
          'Arbetade med att utveckla företagets webbplattform tillsammans med resten av teamet. Teknologier som användes under praktiken inkluderar bland annat: Angular JS, JavaScript, TypeScript och Karma.',
      },
      {
        color: '#d0a77f',
        year: 'Augusti 2020',
        title: 'Introduction to Web Accessibility',
        company: 'W3Cx',
        description: 'Initiative of World Wide Web Consortium.',
      },
      {
        color: '#d0a77f',
        year: 'Vårtermin 2018',
        title: 'Programmering 1',
        company: 'Jensen',
        description: 'Komvux',
      },
      {
        color: '#d0a77f',
        year: 'Vårtermin 2018',
        title: 'Webbutveckling 1',
        company: 'Åsö vuxengymnasium',
        description: 'Komvux',
      },
    ],
  }),
}
</script>
<style scoped>
.even {
  text-align: right;
}

.beige-color {
  color: #d0a77f;
}
</style>
