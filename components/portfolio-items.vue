<template>
  <div class="portfolio-grid">
    <v-hover v-for="(item, i) in items" :key="i" v-slot="{ hover }">
      <v-card class="mx-auto card" color="grey lighten-4">
        <img class="d-flex" :aspect-ratio="16 / 9" :src="item.src" />
        <v-expand-transition>
          <v-overlay
            v-if="hover"
            class="v-card--reveal"
            absolute
            opacity="0.7"
            color="#d0a77f"
          >
            <div class="d-flex flex-column justify-center align-center pa-1">
              <h2>{{ item.title }}</h2>
              <strong>{{ item.skills }}</strong>
              <p class="text-center">
                {{ item.description }}
              </p>
            </div>
            <div v-if="item.giHubUrl || item.siteUrl" class="overlay-btn-box">
              <a v-if="item.gitHubUrl" :href="item.gitHubUrl">
                <v-btn light rounded>GitHub</v-btn>
              </a>
              <a v-if="item.siteUrl" :href="item.siteUrl">
                <v-btn light rounded>Live Site</v-btn>
              </a>
            </div>
            <v-row class="row-width-unset justify-center">
              <v-btn v-if="item.src2" light rounded @click="overlay = !overlay">
                Visa mockup
              </v-btn>
              <v-overlay :z-index="zIndex" :value="overlay">
                <v-btn
                  class="overlay-close-btn ma-3"
                  light
                  rounded
                  @click="overlay = false"
                >
                  <v-icon color="#171b21">mdi-close-thick</v-icon>
                </v-btn>
                <div class="d-flex justify-center align-center overlay-img">
                  <img
                    height="100%"
                    class="image-width-uset"
                    :src="item.src2"
                  />
                </div>
              </v-overlay>
            </v-row>
          </v-overlay>
        </v-expand-transition>
      </v-card>
    </v-hover>
  </div>
</template>
<script>
export default {
  data: () => ({
    overlay: false,
    zIndex: 0,
    items: [
      {
        src: require('../assets/images/portfolio-items/convictus.png'),
        title: 'Convictus',
        skills: 'Nuxt/Contentful/Vuetify/Vuelidate/Vuex-Store/Axios.',
        description:
          'LIA 2 project. Jag jobbade framför allt med förmulär lösningar.',
        siteUrl: 'http://convictus.org/',
      },
      {
        src: require('../assets/images/portfolio-items/wcagnetworks.png'),
        title: 'WCAG Networks',
        skills: 'Nuxt/Contentful/Vuetify.',
        description: 'Digital tillgänglighet och WCAG-riktlinjerna.',
        siteUrl: 'https://wcagnetworks.com/',
      },
      {
        src: require('../assets/images/portfolio-items/b3squadra.png'),
        title: 'B3 Squadra',
        skills: 'Nuxt/Contentful/Vuetify/Vuelidate/Vuex-Store/Axios.',
        description:
          'Webbplats byggd tillsammans med två klasskamrater under vår examensarbete. Webbplatsen blev inte publicerat.',
        url: '',
      },
      {
        src: require('../assets/images/portfolio-items/bandsite.png'),
        title: 'Band Site - Bob Marley',
        skills: 'Jekyll/Netlify/Sass/JavaScript',
        description: 'Grupparbete under kursen JavaScript 3.',
        siteUrl: 'https://flamboyant-curie-65a21c.netlify.com/',
        gitHubUrl: 'https://github.com/vsarrocchi/band-site',
      },
      {
        src: require('../assets/images/portfolio-items/webshop.png'),
        title: 'Life Hacks - Webshop',
        skills: 'JavaScript/CSS/AJAX/XML/JSON/jQuery/Web-Storage-API',
        description: 'Grupparbete under kursen JavaScript 2.',
        siteUrl: 'https://lezcodeher.github.io/project-webshop/',
        gitHubUrl: 'https://github.com/vsarrocchi/project-webshop-1',
      },
      {
        src: require('../assets/images/portfolio-items/artgallery.png'),
        title: 'Live Art Gallery',
        skills: 'JavaScript/HTML/CSS',
        description: 'Projekt gjort under Frontendprojekt kursen.',
        siteUrl: 'https://vsarrocchi.github.io/FrontendProjekt-Projekt2/',
        gitHubUrl: 'https://github.com/vsarrocchi/FrontendProjekt-Projekt2',
      },
      {
        src: require('../assets/images/portfolio-items/superhero.png'),
        title: 'SuperHero for hire',
        skills: 'JavaScript/JSON/HTML/CSS/Sass',
        description: 'Grupparbete under kursen Frontend Projekt.',
        siteUrl: 'https://mmdarrah.github.io/SuperHero4rent/',
        gitHubUrl: 'https://github.com/vsarrocchi/SuperHero4rent',
      },
      {
        src: require('../assets/images/portfolio-items/flexboxgrid.png'),
        title: 'Flexbox/Grid',
        skills: 'HTML/CSS/Sass',
        description: 'Grupparbete under kursen HTML och CSS.',
        siteUrl: 'https://vsarrocchi.github.io/Projektarbete-HTML-CSS/',
        gitHubUrl: 'https://github.com/vsarrocchi/Projektarbete-HTML-CSS',
      },
      {
        src: require('../assets/images/portfolio-items/grafikverktig2.png'),
        title: 'Art Gallery - Mockup',
        skills: 'Photoshop/Illustratorss',
        description: 'Projekt gjort under Grafik Verktig kursen.',
        src2: require('../assets/images/portfolio-items/grafikverktig.jpg'),
      },
      {
        src: require('../assets/images/portfolio-items/journal.png'),
        title: 'Journal',
        skills: 'PHP/SQL/MySQL/JavaScript/HTML/CSS',
        description:
          'Projekt gjort under CMS-verktyg, backend och interaktion med databaser kursen.',
        gitHubUrl: 'https://github.com/vsarrocchi/PHP_MySQL_Journal',
      },
      {
        src: require('../assets/images/portfolio-items/thirdportfolio.png'),
        title: 'Min tredje portfölj',
        skills: 'Nuxt/JavaScript/Tailwind',
        description: '',
        siteUrl: 'https://vsarrocchi.netlify.app/',
        gitHubUrl: 'https://github.com/vsarrocchi/nuxt-portfolio',
      },
      {
        src: require('../assets/images/portfolio-items/secondportfolio.png'),
        title: 'Min andra portfölj',
        skills: 'Gatsby/React/Netlify/JavaScript/CSS',
        description: '',
        siteUrl: 'https://vssportfolio.netlify.app',
        gitHubUrl: 'https://github.com/vsarrocchi/vs_portfolio',
      },
      {
        src: require('../assets/images/portfolio-items/firstportfolio.png'),
        title: 'Min första portfölj',
        skills: 'HTML/CSS/JavaScript',
        description: '',
        siteUrl: 'https://vsarrocchi.github.io/Portfolio/',
        gitHubUrl: 'https://github.com/vsarrocchi/Portfolio',
      },
    ],
  }),
}
</script>
<style lang="scss">
.portfolio-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 20px;
  .card {
    .image-width-uset {
      width: unset !important;
    }
    img {
      width: 100%;
      border-radius: 3px;
    }
  }
}

.v-card--reveal {
  padding: 10px;
  width: 100%;
  .row-width-unset {
    width: unset;
  }
  div {
    width: 100%;
    h2 {
      color: #171b21;
      text-align: center;
    }
    strong {
      color: #171b21;
      text-align: center;
    }
    p {
      text-align: center;
      color: #171b21;
    }
    a {
      text-decoration: none;
    }
  }
}

.row.grafikverktig-img-overlay div {
  width: unset !important;
}

.overlay-btn-box {
  width: 100%;
  display: flex;
  justify-content: space-evenly;
}

.overlay-close-btn {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 1000;
}

.overlay-img {
  width: 100vw;
  height: 100vh;
}

@media (min-width: 768px) {
  .portfolio-grid {
    grid-template-columns: 1fr 1fr;
  }
}

@media (min-width: 960px) {
  .portfolio-grid {
    grid-template-columns: 1fr 1fr;
  }
}

@media (min-width: 1400px) {
  .portfolio-grid {
    grid-template-columns: 1fr 1fr 1fr;
  }
}
</style>
