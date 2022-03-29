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
          Hej! Mitt namn är Valesca och jag är en junior Frontend utvecklare
          bosatt i Stockholm. Jag tog examen i maj 2020 i Nackademin och har
          drygt ett års arbetserfarenhet som Frontend utvecklare.
        </p>
        <p class="om-mig-text py-4">
          Mitt mål är att hitta en plats där jag kan fortsätta att förbättra
          mina färdigheter som utvecklare, samtidigt som jag känner mig genuint
          motiverad att arbeta tillsammans med mina kollegor och med de projekt
          jag är tilldelad.
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
        <TimeLine />
      </v-col>
    </v-row>
    <v-row class="om-mig-content text-center mx-0">
      <v-col class="pa-0">
        <h2 class="om-mig-h2 pb-12">Tekniska Kompetenser</h2>
        <div>
          <div class="pb-12 d-flex justify-center flex-wrap">
            <div v-for="(item, i) in skills" :key="i" class="skills-box">
              <v-sheet
                v-if="item.type === 'first'"
                class="pa-5 ma-5 text-center"
                color="white"
                elevation="5"
              >
                <img
                  :src="require(`../assets/images/svg/${item.url}`)"
                  :alt="item.name"
                />
                <br />
                <span>{{ item.name }}</span>
              </v-sheet>
            </div>
          </div>
          <strong class="my-5"
            >Jag har också blivit bekant med dessa tekniker</strong
          >
          <div class="pb-12">
            <div class="d-flex justify-center flex-wrap">
              <div
                v-for="(item, index) in skills"
                :key="index"
                class="skills-box"
              >
                <v-sheet
                  v-if="item.type === 'second'"
                  class="pa-5 ma-5 text-center"
                  color="white"
                  elevation="5"
                >
                  <img
                    class="pa-0 ma-0"
                    :src="require(`../assets/images/svg/${item.url}`)"
                    :alt="item.name"
                  />
                  <br />
                  <span>{{ item.name }}</span>
                </v-sheet>
              </div>
            </div>
          </div>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data: () => ({
    skills: [
      {
        type: 'first',
        url: 'javascript.svg',
        name: 'JavaScript',
      },
      {
        type: 'first',
        url: 'html5.svg',
        name: 'HTML5',
      },
      {
        type: 'first',
        url: 'css3.svg',
        name: 'CSS3',
      },
      {
        type: 'first',
        url: 'angular.svg',
        name: 'Angular',
      },
      {
        type: 'first',
        url: 'nuxt.svg',
        name: 'Nuxt',
      },
      {
        type: 'first',
        url: 'vue.svg',
        name: 'Vue',
      },
      {
        type: 'first',
        url: 'react.svg',
        name: 'React',
      },
      {
        type: 'first',
        url: 'contentful.svg',
        name: 'Contentful',
      },
      {
        type: 'first',
        url: 'vuetify.svg',
        name: 'Vuetify',
      },
      {
        type: 'first',
        url: 'sass.svg',
        name: 'Sass',
      },
      {
        type: 'first',
        url: 'bootstrap.svg',
        name: 'Bootstrap',
      },
      {
        type: 'first',
        url: 'tailwind.svg',
        name: 'Tailwind',
      },
      {
        type: 'first',
        url: 'git.svg',
        name: 'Git',
      },
      {
        type: 'first',
        url: 'github.svg',
        name: 'GitHub',
      },
      {
        type: 'first',
        url: 'responsive-design.svg',
        name: 'Responsive design',
      },
      {
        type: 'first',
        url: 'w3c.svg',
        name: 'Introduction to Web Accessibility',
      },
      {
        type: 'second',
        url: 'gimp.svg',
        name: 'Gimp',
      },
      {
        type: 'second',
        url: 'figma.svg',
        name: 'Figma',
      },
      {
        type: 'second',
        url: 'photoshop.svg',
        name: 'Adobe Photoshop',
      },
      {
        type: 'second',
        url: 'illustrator.svg',
        name: 'Adobe Illustrator',
      },
      {
        type: 'second',
        url: 'xd.svg',
        name: 'Adobe XD',
      },
      {
        type: 'second',
        url: 'gatsby.svg',
        name: 'Gatsby',
      },
      {
        type: 'second',
        url: 'typescript.svg',
        name: 'TypeScript',
      },
      {
        type: 'second',
        url: 'wordpress.svg',
        name: 'Wordpress',
      },
      {
        type: 'second',
        url: 'php.svg',
        name: 'PHP',
      },
      {
        type: 'second',
        url: 'mysql.svg',
        name: 'MySQL',
      },
      {
        type: 'second',
        url: 'firebase.svg',
        name: 'Firebase',
      },
      {
        type: 'second',
        url: 'netlify.svg',
        name: 'Netlify',
      },
    ],
  }),
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

.om-mig-h2 {
  color: #171b21;
  font-size: 3rem !important;
}

.skills-box {
  display: flex;
  align-items: flex-end;
  height: 200px;
}

.skills-box img {
  height: 50px;
}

.adobe-icon {
  border: 4px solid #d0a77f;
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
