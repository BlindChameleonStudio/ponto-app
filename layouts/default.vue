<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-tile
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-toolbar-side-icon @click="drawer = !drawer" />




    </v-toolbar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
    </v-navigation-drawer>
    <v-footer
      :fixed="fixed"
      app
    >
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'apps',
          title: 'O nás',
          to: '/'
        },
        {
          icon: 'bubble_chart',
          title: 'O projektu',
          to: '/projects'
        },
        {
          icon: 'bubble_chart',
          title: 'Články',
          to: '/articles'
        },
        {
          icon: 'bubble_chart',
          title: 'Přednášky',
          to: '/lectures'
        },
        {
          icon: 'bubble_chart',
          title: 'Zapojte se',
          to: '/get-involved'
        },
        {
          icon: 'bubble_chart',
          title: 'Kontakt',
          to: '/contact'
        },
        {
          icon: 'bubble_chart',
          title: 'Kontakt',
          to: '/give-me-your-money'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>
