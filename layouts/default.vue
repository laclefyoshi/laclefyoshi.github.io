<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      width="130"
      fixed
      app
      >
      <v-list>
        <v-list-tile
          router
          :to="item.to"
          :key="i"
          v-for="(item, i) in items"
          exact
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar>
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
    </v-toolbar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>&copy; 2015- 佐伯嘉康 / Yoshiyasu SAEKI</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        drawer: null,
        fixed: true,
        items: [
          { icon: 'apps', title: 'Top', to: '/' },
          { icon: 'bubble_chart', title: 'Works', to: '/works' },
          { icon: 'bubble_chart', title: 'Links', to: '/links' }
        ]
      }
    }
  }
</script>
