<template>
  <nav>
    <v-app-bar class="rounded-br-xl" width="60" color="#d0a77f" fixed>
      <v-btn
        color="#171b21"
        icon
        x-large
        @click.stop="rightDrawer = !rightDrawer"
      >
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
</template>

<script>
export default {
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
        // {
        //   icon: 'mdi-briefcase',
        //   title: 'Portfolio',
        //   to: '/portfolio',
        // },
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
