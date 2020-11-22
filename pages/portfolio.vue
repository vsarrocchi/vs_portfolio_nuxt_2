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
        <div class="portfolio-grid">
          <!-- Convictus -->
          <v-hover v-slot="{ hover }">
            <v-card class="mx-auto portfolio-card" color="grey lighten-4">
              <img
                class="d-flex portfolio-img"
                :aspect-ratio="16 / 9"
                :src="require('../assets/images/portfolio-items/convictus.png')"
              />
              <v-expand-transition>
                <v-overlay
                  v-if="hover"
                  class="v-card--reveal"
                  absolute
                  opacity="0.7"
                  color="#d0a77f"
                >
                  <div
                    class="d-flex flex-column justify-center align-center pa-1"
                  >
                    <h2>Convictus</h2>
                    <strong
                      >Nuxt/Contentful/Vuetify/Vuelidate/Vuex-Store/Axios.</strong
                    >
                    <p class="text-center">
                      Webbplats byggd tillsammans med två klasskamrater under
                      vår LIA 2.
                    </p>
                    <a href="http://convictus.org/">
                      <v-btn color="#171b21" rounded outlined
                        >Besök Convictus webbplats
                      </v-btn>
                    </a>
                  </div>
                </v-overlay>
              </v-expand-transition>
            </v-card>
          </v-hover>
          <!-- WCAG Networks -->
          <v-hover v-slot="{ hover }">
            <v-card class="mx-auto portfolio-card" color="grey lighten-4">
              <img
                class="d-flex portfolio-img"
                :aspect-ratio="16 / 9"
                :src="
                  require('../assets/images/portfolio-items/wcagnetworks.png')
                "
              />
              <v-expand-transition>
                <v-overlay
                  v-if="hover"
                  class="v-card--reveal"
                  absolute
                  opacity="0.7"
                  color="#d0a77f"
                >
                  <div
                    class="d-flex flex-column justify-center align-center pa-1"
                  >
                    <h2>WCAG Networks</h2>
                    <strong>Nuxt/Contentful/Vuetify.</strong>
                    <p class="text-center">
                      Webbplats byggd med digital tillgänglighet och
                      WCAG-riktlinjerna i fokus.
                    </p>
                    <a href="https://wcagnetworks.com/">
                      <v-btn color="#171b21" rounded outlined
                        >Besök WCAG Networks webbplats
                      </v-btn>
                    </a>
                  </div>
                </v-overlay>
              </v-expand-transition>
            </v-card>
          </v-hover>
          <!-- B3 Squadra -->
          <v-hover v-slot="{ hover }">
            <v-card class="mx-auto portfolio-card" color="grey lighten-4">
              <img
                class="d-flex portfolio-img"
                :aspect-ratio="16 / 9"
                :src="require('../assets/images/portfolio-items/b3squadra.png')"
              />
              <v-expand-transition>
                <v-overlay
                  v-if="hover"
                  class="v-card--reveal"
                  absolute
                  opacity="0.7"
                  color="#d0a77f"
                >
                  <div class="d-flex flex-column justify-center align-center">
                    <h2>B3 Squadra</h2>
                    <strong
                      >Nuxt/Contentful/Vuetify/Vuelidate/Vuex-Store/Axios.</strong
                    >
                    <p class="text-center">
                      Webbplats byggd tillsammans med två klasskamrater under
                      vår examensarbete. Webbplatsen blev inte publicerat.
                    </p>
                    <v-row justify="center">
                      <v-btn
                        v-click-outside="onClickOutside"
                        color="#171b21"
                        rounded
                        outlined
                        @click="
                          overlay = !overlay
                          active = true
                        "
                      >
                        Visa webbplatsens bilder
                      </v-btn>
                      <v-overlay :z-index="zIndex" :value="overlay">
                        <v-btn
                          class="white--text overlay-close-btn ma-3"
                          color="#d0a77f"
                          rounded
                          @click="overlay = false"
                        >
                          <v-icon color="#171b21">mdi-close-thick</v-icon>
                        </v-btn>
                        <div
                          class="d-flex justify-center align-center overlay-img"
                        >
                          <v-carousel height="auto" class="carousel">
                            <v-carousel-item
                              v-for="(bild, i) in carouselImages"
                              :key="i"
                              :src="bild.src"
                              class="carousel-item"
                            ></v-carousel-item>
                          </v-carousel>
                        </div>
                      </v-overlay>
                    </v-row>
                  </div>
                </v-overlay>
              </v-expand-transition>
            </v-card>
          </v-hover>
          <!-- Band Site -->
          <v-hover v-slot="{ hover }">
            <v-card class="mx-auto portfolio-card" color="grey lighten-4">
              <img
                class="d-flex portfolio-img"
                :aspect-ratio="16 / 9"
                :src="require('../assets/images/portfolio-items/bandsite.png')"
              />
              <v-expand-transition>
                <v-overlay
                  v-if="hover"
                  class="v-card--reveal"
                  absolute
                  opacity="0.7"
                  color="#d0a77f"
                >
                  <div
                    class="d-flex flex-column justify-center align-center pa-1"
                  >
                    <h2>Band Site - Bob Marley</h2>
                    <strong>Jekyll/Netlify/Sass/JavaScript</strong>
                    <p class="text-center">
                      Projekt gjort tillsammans med två klasskamrater under
                      kursen JavaScript 3.
                    </p>
                    <a href="https://flamboyant-curie-65a21c.netlify.com/">
                      <v-btn color="#171b21" rounded outlined
                        >Besök Band Site projektet
                      </v-btn></a
                    >
                  </div>
                </v-overlay>
              </v-expand-transition>
            </v-card>
          </v-hover>
          <!-- Webshop -->
          <v-hover v-slot="{ hover }">
            <v-card class="mx-auto portfolio-card" color="grey lighten-4">
              <img
                class="d-flex portfolio-img"
                :aspect-ratio="16 / 9"
                :src="require('../assets/images/portfolio-items/webshop.png')"
              />
              <v-expand-transition>
                <v-overlay
                  v-if="hover"
                  class="v-card--reveal"
                  absolute
                  opacity="0.7"
                  color="#d0a77f"
                >
                  <div
                    class="d-flex flex-column justify-center align-center pa-1"
                  >
                    <h2>Life Hacks - Webshop</h2>
                    <strong
                      >JavaScript/CSS/AJAX/XML/JSON/jQuery/Web-Storage-API</strong
                    >
                    <p class="text-center">
                      Projekt gjort tillsammans med en klasskamrat under kursen
                      JavaScript 2.
                    </p>
                    <a href="https://lezcodeher.github.io/project-webshop/">
                      <v-btn color="#171b21" rounded outlined
                        >Besök Webbshop projektet
                      </v-btn></a
                    >
                  </div>
                </v-overlay>
              </v-expand-transition>
            </v-card>
          </v-hover>
          <!-- Art Gallery -->
          <v-hover v-slot="{ hover }">
            <v-card class="mx-auto portfolio-card" color="grey lighten-4">
              <img
                class="d-flex portfolio-img"
                :aspect-ratio="16 / 9"
                :src="
                  require('../assets/images/portfolio-items/artgallery.png')
                "
              />
              <v-expand-transition>
                <v-overlay
                  v-if="hover"
                  class="v-card--reveal"
                  absolute
                  opacity="0.7"
                  color="#d0a77f"
                >
                  <div
                    class="d-flex flex-column justify-center align-center pa-1"
                  >
                    <h2>Live Art Gallery</h2>
                    <strong>JavaScript/HTML/CSS</strong>
                    <p class="text-center">
                      Projekt gjort under Frontendprojekt kursen.
                    </p>
                    <a
                      href="https://vsarrocchi.github.io/FrontendProjekt-Projekt2/"
                    >
                      <v-btn color="#171b21" rounded outlined
                        >Besök Live Art Gallery projektet
                      </v-btn></a
                    >
                  </div>
                </v-overlay>
              </v-expand-transition>
            </v-card>
          </v-hover>
          <!-- Super Hero -->
          <v-hover v-slot="{ hover }">
            <v-card class="mx-auto portfolio-card" color="grey lighten-4">
              <img
                class="d-flex portfolio-img"
                :aspect-ratio="16 / 9"
                :src="require('../assets/images/portfolio-items/superhero.png')"
              />
              <v-expand-transition>
                <v-overlay
                  v-if="hover"
                  class="v-card--reveal"
                  absolute
                  opacity="0.7"
                  color="#d0a77f"
                >
                  <div
                    class="d-flex flex-column justify-center align-center pa-1"
                  >
                    <h2>SuperHero for hire</h2>
                    <strong>JavaScript/JSON/HTML/CSS/Sass</strong>
                    <p class="text-center">
                      Projekt gjort tillsammans med tre klasskamrater under
                      kursen Frontend Projekt.
                    </p>
                    <a href="https://mmdarrah.github.io/SuperHero4rent/">
                      <v-btn color="#171b21" rounded outlined
                        >Besök SuperHero for hire projektet
                      </v-btn></a
                    >
                  </div>
                </v-overlay>
              </v-expand-transition>
            </v-card>
          </v-hover>
          <!-- Flexbox/Grid -->
          <v-hover v-slot="{ hover }">
            <v-card class="mx-auto portfolio-card" color="grey lighten-4">
              <img
                class="d-flex portfolio-img"
                :aspect-ratio="16 / 9"
                :src="
                  require('../assets/images/portfolio-items/flexboxgrid.png')
                "
              />
              <v-expand-transition>
                <v-overlay
                  v-if="hover"
                  class="v-card--reveal"
                  absolute
                  opacity="0.7"
                  color="#d0a77f"
                >
                  <div
                    class="d-flex flex-column justify-center align-center pa-1"
                  >
                    <h2>Flexbox/Grid</h2>
                    <strong>HTML/CSS/Sass</strong>
                    <p class="text-center">
                      Projekt gjort tillsammans med en klasskamrat under kursen
                      HTML och CSS.
                    </p>
                    <a
                      href="https://vsarrocchi.github.io/Projektarbete-HTML-CSS/"
                    >
                      <v-btn color="#171b21" rounded outlined
                        >Besök Flexbox/Grid projektet
                      </v-btn></a
                    >
                  </div>
                </v-overlay>
              </v-expand-transition>
            </v-card>
          </v-hover>
          <!-- Grafikverktig -->
          <v-hover v-slot="{ hover }">
            <v-card class="mx-auto portfolio-card" color="grey lighten-4">
              <img
                class="d-flex portfolio-img"
                :aspect-ratio="16 / 9"
                :src="
                  require('../assets/images/portfolio-items/grafikverktig2.png')
                "
              />
              <v-expand-transition>
                <v-overlay
                  v-if="hover"
                  class="v-card--reveal"
                  absolute
                  opacity="0.7"
                  color="#d0a77f"
                >
                  <div class="d-flex flex-column justify-center align-center">
                    <h2>Art Gallery - Mockup</h2>
                    <strong>Photoshop/Illustrator</strong>
                    <p class="text-center">
                      Projekt gjort under Grafik Verktig kursen.
                    </p>
                    <v-row justify="center">
                      <v-btn
                        color="#171b21"
                        rounded
                        outlined
                        @click="overlay = !overlay"
                      >
                        Visa Art Gallery mockup
                      </v-btn>

                      <v-overlay :z-index="zIndex" :value="overlay">
                        <v-btn
                          class="white--text overlay-close-btn ma-3"
                          color="#d0a77f"
                          rounded
                          @click="overlay = false"
                        >
                          <v-icon color="#171b21">mdi-close-thick</v-icon>
                        </v-btn>
                        <div
                          class="d-flex justify-center align-center overlay-img"
                        >
                          <img
                            height="100%"
                            :src="
                              require('../assets/images/portfolio-items/grafikverktig.jpg')
                            "
                          />
                        </div>
                      </v-overlay>
                    </v-row>
                  </div>
                </v-overlay>
              </v-expand-transition>
            </v-card>
          </v-hover>
          <!-- Journal -->
          <v-hover v-slot="{ hover }">
            <v-card
              class="mx-auto portfolio-card d-flex"
              color="grey lighten-4"
            >
              <img
                class="d-flex portfolio-img"
                :aspect-ratio="16 / 9"
                :src="require('../assets/images/portfolio-items/journal.png')"
              />
              <v-expand-transition>
                <v-overlay
                  v-if="hover"
                  class="v-card--reveal"
                  absolute
                  opacity="0.7"
                  color="#d0a77f"
                >
                  <div class="d-flex flex-column justify-center align-center">
                    <h2>Journal</h2>
                    <strong>PHP/SQL/MySQL/JavaScript/HTML/CSS</strong>
                    <p class="text-center">
                      Projekt gjort under CMS-verktyg, backend och interaktion
                      med databaser kursen.
                    </p>
                    <a href="">
                      <v-btn color="#171b21" rounded outlined
                        >Besök Journal projektet
                      </v-btn></a
                    >
                  </div>
                </v-overlay>
              </v-expand-transition>
            </v-card>
          </v-hover>
          <!-- Third Portfolio -->
          <v-hover v-slot="{ hover }">
            <v-card class="mx-auto portfolio-card" color="grey lighten-4">
              <img
                class="d-flex portfolio-img"
                :aspect-ratio="16 / 9"
                :src="
                  require('../assets/images/portfolio-items/thirdportfolio.png')
                "
              />
              <v-expand-transition>
                <v-overlay
                  v-if="hover"
                  class="v-card--reveal"
                  absolute
                  opacity="0.7"
                  color="#d0a77f"
                >
                  <div
                    class="d-flex flex-column justify-center align-center pa-1"
                  >
                    <h2>Min tredje portfölj</h2>
                    <strong>Nuxt/JavaScript/Tailwind</strong>
                    <a href="https://vsarrocchi.netlify.app/">
                      <v-btn color="#171b21" rounded outlined
                        >Besök min tredje portfölj
                      </v-btn></a
                    >
                  </div>
                </v-overlay>
              </v-expand-transition>
            </v-card>
          </v-hover>
          <!-- Second Portfolio -->
          <v-hover v-slot="{ hover }">
            <v-card class="mx-auto portfolio-card" color="grey lighten-4">
              <img
                class="d-flex portfolio-img"
                :aspect-ratio="16 / 9"
                :src="
                  require('../assets/images/portfolio-items/secondportfolio.png')
                "
              />
              <v-expand-transition>
                <v-overlay
                  v-if="hover"
                  class="v-card--reveal"
                  absolute
                  opacity="0.7"
                  color="#d0a77f"
                >
                  <div
                    class="d-flex flex-column justify-center align-center pa-1"
                  >
                    <h2>Min andra portfölj</h2>
                    <strong>Gatsby/React/Netlify/JavaScript/CSS</strong>
                    <a href="https://vssportfolio.netlify.app">
                      <v-btn color="#171b21" rounded outlined
                        >Besök min andra portfölj
                      </v-btn></a
                    >
                  </div>
                </v-overlay>
              </v-expand-transition>
            </v-card>
          </v-hover>
          <!-- First Portfolio -->
          <v-hover v-slot="{ hover }">
            <v-card class="mx-auto portfolio-card" color="grey lighten-4">
              <img
                class="d-flex portfolio-img"
                :aspect-ratio="16 / 9"
                :src="
                  require('../assets/images/portfolio-items/firstportfolio.png')
                "
              />
              <v-expand-transition>
                <v-overlay
                  v-if="hover"
                  class="v-card--reveal"
                  absolute
                  opacity="0.7"
                  color="#d0a77f"
                >
                  <div
                    class="d-flex flex-column justify-center align-center pa-1"
                  >
                    <h2>Min första portfölj</h2>
                    <strong>HTML/CSS/JavaScript</strong>
                    <a href="https://vsarrocchi.github.io/Portfolio/">
                      <v-btn color="#171b21" rounded outlined
                        >Besök min första portfölj
                      </v-btn></a
                    >
                  </div>
                </v-overlay>
              </v-expand-transition>
            </v-card>
          </v-hover>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data: () => ({
    overlay: false,
    zIndex: 0,
    active: false,
    carouselImages: [
      {
        src: require('../assets/images/portfolio-items/b3squadra1.png'),
      },
      {
        src: require('../assets/images/portfolio-items/b3squadra2.png'),
      },
      {
        src: require('../assets/images/portfolio-items/b3squadra3.png'),
      },
      {
        src: require('../assets/images/portfolio-items/b3squadra4.png'),
      },
      {
        src: require('../assets/images/portfolio-items/b3squadra5.png'),
      },
    ],
  }),
  methods: {
    onClickOutside() {
      this.active = false
    },
  },
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
  .portfolio-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 20px;
    .portfolio-card {
      .portfolio-img {
        width: 100%;
        border-radius: 3px;
      }
    }
  }
}

.v-card--reveal {
  div {
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

.carousel-item {
  width: 30%;
  margin: auto;
}

@media (min-width: 768px) {
  .portfolio-content {
    padding: 56px 10%;
    .portfolio-grid {
      grid-template-columns: 1fr 1fr;
    }
  }
}

@media (min-width: 960px) {
  .portfolio-content {
    padding: 15vh 10%;
    .portfolio-grid {
      grid-template-columns: 1fr 1fr;
    }
  }
}

@media (min-width: 1400px) {
  .portfolio-content {
    .portfolio-grid {
      grid-template-columns: 1fr 1fr 1fr;
    }
  }
}
</style>
