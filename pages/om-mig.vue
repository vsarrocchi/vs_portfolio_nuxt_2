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
          Hej! Mitt namn är Valesca och jag är en Frontend utvecklare bosatt i
          Stockholm. Jag tog examen i maj det här året i Nackademin och efter
          det jobbade jag deltid i företaget WCAG Networks där jag fick
          möjlighet att lära mig om digital tillgänglighet och WCAG
          riktlinjerna. Just nu söker jag ett jobb där jag kan fortsätta min
          utveckling som Frontend utvecklare.
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
    <v-row class="om-mig-content text-center mx-0">
      <v-col class="pa-0">
        <h2 class="om-mig-h2 pb-12">Tekniska Kompetenser</h2>
        <div>
          <div class="pb-12">
            <div class="d-flex justify-center flex-wrap">
              <div v-for="(item, i) in skills" :key="i">
                <v-sheet
                  v-if="item.type === 'first'"
                  class="pa-5 ma-5 text-center skills-box"
                  color="white"
                  elevation="5"
                >
                  <v-icon v-if="item.icon">{{ item.icon }}</v-icon>
                  <img
                    v-if="item.url && item.name === 'Adobe Photoshop'"
                    class="pa-0 ma-0 adobe-icon"
                    src="../assets/images/om-oss-logotyper/Photoshop.svg"
                    :alt="item.name"
                  />
                  <img
                    v-if="item.url && item.name === 'Adobe Illustrator'"
                    class="pa-0 ma-0 adobe-icon"
                    src="../assets/images/om-oss-logotyper/Illustrator.svg"
                    :alt="item.name"
                  />
                  <img
                    v-if="item.url && item.name === 'Adobe XD'"
                    class="pa-0 ma-0 adobe-icon"
                    src="../assets/images/om-oss-logotyper/XD.svg"
                    :alt="item.name"
                  />
                  <img
                    v-if="item.url && item.name === 'Gimp'"
                    class="gimp-icon"
                    src="../assets/images/om-oss-logotyper/gimp.svg"
                    :alt="item.name"
                  />
                  <img
                    v-if="item.url && item.name === 'Figma'"
                    src="../assets/images/om-oss-logotyper/figma.svg"
                    :alt="item.name"
                  />
                  <img
                    v-if="item.url && item.name === 'Contentful'"
                    src="../assets/images/om-oss-logotyper/contentful.svg"
                    :alt="item.name"
                  />
                  <img
                    v-if="item.url && item.url === 'w3c'"
                    src="../assets/images/om-oss-logotyper/w3c.svg"
                    :alt="item.name"
                  />
                  <br />
                  <span>{{ item.name }}</span>
                </v-sheet>
              </div>
            </div>
          </div>
          <strong class="my-5"
            >Jag har också blivit bekant med dessa tekniker</strong
          >
          <div class="pb-12">
            <div class="d-flex justify-center flex-wrap">
              <div v-for="(item, index) in skills" :key="index">
                <v-sheet
                  v-if="item.type === 'second'"
                  class="pa-5 ma-5 text-center skills-box"
                  color="white"
                  elevation="5"
                >
                  <v-icon>{{ item.icon }}</v-icon>
                  <img
                    v-if="item.url && item.name === 'Jasmine'"
                    src="../assets/images/om-oss-logotyper/jasmine.svg"
                    :alt="item.name"
                  />
                  <img
                    v-if="item.url && item.name === 'Karma'"
                    src="../assets/images/om-oss-logotyper/karma.svg"
                    :alt="item.name"
                  />
                  <img
                    v-if="item.url && item.name === 'Jest'"
                    src="../assets/images/om-oss-logotyper/jest.svg"
                    :alt="item.name"
                  />
                  <img
                    v-if="item.url && item.name === 'MySQL'"
                    src="../assets/images/om-oss-logotyper/mysql.svg"
                    :alt="item.name"
                  />
                  <img
                    v-if="item.url && item.name === 'Netlify'"
                    class="my-3"
                    src="../assets/images/om-oss-logotyper/netlify.svg"
                    :alt="item.name"
                  />
                  <img
                    v-if="item.url && item.name === 'Jekyll'"
                    src="../assets/images/om-oss-logotyper/jekyll.svg"
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
        icon: 'mdi-language-javascript',
        name: 'JavaScript',
      },
      {
        type: 'first',
        icon: 'mdi-language-html5',
        name: 'HTML5',
      },
      {
        type: 'first',
        icon: 'mdi-language-css3',
        name: 'CSS3',
      },
      {
        type: 'first',
        icon: 'mdi-vuejs',
        name: 'Vue',
      },
      {
        type: 'first',
        icon: 'mdi-nuxt',
        name: 'Nuxt',
      },
      {
        type: 'first',
        url: '../assets/images/contentful.svg',
        name: 'Contentful',
      },
      {
        type: 'first',
        icon: 'mdi-jquery',
        name: 'jQuery',
      },
      {
        type: 'first',
        icon: 'mdi-git',
        name: 'Git',
      },
      {
        type: 'first',
        icon: 'mdi-github',
        name: 'GitHub',
      },
      {
        type: 'first',
        icon: 'mdi-vuetify',
        name: 'Vuetify',
      },
      {
        type: 'first',
        icon: 'mdi-sass',
        name: 'Sass',
      },
      {
        type: 'first',
        icon: 'mdi-bootstrap',
        name: 'Bootstrap',
      },
      {
        type: 'first',
        icon: 'mdi-tailwind',
        name: 'Tailwind',
      },
      {
        type: 'first',
        url: '../assets/images/gimp.png',
        name: 'Gimp',
      },
      {
        type: 'first',
        url: '../assets/images/figma.svg',
        name: 'Figma',
      },
      {
        type: 'first',
        url: '../assets/images/Photoshop.svg',
        name: 'Adobe Photoshop',
      },
      {
        type: 'first',
        url: '../assets/images/Illustrator.svg',
        name: 'Adobe Illustrator',
      },
      {
        type: 'first',
        url: '../assets/images/XD.svg',
        name: 'Adobe XD',
      },
      {
        type: 'first',
        icon: 'mdi-responsive',
        name: 'Responsive Design',
      },
      {
        type: 'first',
        url: 'w3c',
        name: 'Introduction to Web Accessibility',
      },
      {
        type: 'second',
        icon: 'mdi-react',
        name: 'Ract',
      },
      {
        type: 'second',
        icon: 'mdi-gatsby',
        name: 'Gatsby',
      },
      {
        type: 'second',
        icon: 'mdi-angular',
        name: 'Angular',
      },
      {
        type: 'second',
        icon: 'mdi-language-typescript',
        name: 'TypeScript',
      },
      {
        type: 'second',
        icon: 'mdi-wordpress',
        name: 'Wordpress',
      },
      {
        type: 'second',
        icon: 'mdi-language-php',
        name: 'PHP',
      },
      {
        type: 'second',
        url: 'MySQL',
        name: 'MySQL',
      },
      {
        type: 'second',
        url: 'mdi-language-php',
        name: 'Jasmine',
      },
      {
        type: 'second',
        url: 'mdi-language-php',
        name: 'Karma',
      },
      {
        type: 'second',
        url: 'mdi-language-php',
        name: 'Jest',
      },
      {
        type: 'second',
        icon: 'mdi-firebase',
        name: 'Firebase',
      },
      {
        type: 'second',
        url: 'mdi-',
        name: 'Netlify',
      },
      {
        type: 'second',
        url: 'mdi-',
        name: 'Jekyll',
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
  // letter-spacing: 0.05em;
  // line-height: 1.8em;
  font-size: 1.3rem;
}

.om-mig-h2 {
  color: #171b21;
  font-size: 3rem !important;
}

.skills-box {
  min-height: 156px;
  .v-icon {
    font-size: 5rem;
    color: #d0a77f !important;
  }
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
