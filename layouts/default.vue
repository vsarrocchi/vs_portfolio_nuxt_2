<template>
  <v-app>
    <nav>
      <v-app-bar class="rounded-br-xl" width="60" color="#d0a77f" fixed>
        <v-btn
          color="#171b21"
          icon
          x-large
          @click.stop="rightDrawer = !rightDrawer"
        >
          <!-- <v-btn
          :aria-expanded="active ? 'true' : 'false'"
          @click="active = !active"
        ></v-btn> -->
          <v-icon>mdi-menu</v-icon>
        </v-btn>
      </v-app-bar>
      <v-navigation-drawer
        v-model="rightDrawer"
        :right="right"
        color="#171b21"
        temporary
        fixed
        dark
      >
        <v-list>
          <v-list-item
            v-for="(item, i) in items"
            :key="i"
            :to="item.to"
            router
            exact
          >
            <v-list-item-action>
              <v-icon color="#d0a77f">{{ item.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title v-text="item.title" />
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    </nav>
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

export default {
  components: {
    Social,
  },
  data() {
    return {
      items: [
        {
          icon: 'mdi-home',
          title: 'Hem',
          to: '/',
        },
        {
          icon: 'mdi-card-account-details',
          title: 'Om mig',
          to: '/om-mig',
        },
        {
          icon: 'mdi-briefcase',
          title: 'Portfolio',
          to: '/portfolio',
        },
        {
          icon: 'mdi-email',
          title: 'Kontakt',
          to: '/kontakt',
        },
      ],
      right: false,
      rightDrawer: false,
    }
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

.border {
  border: 1px solid red;
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
