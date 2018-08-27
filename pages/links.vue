<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <v-card>
        <v-toolbar>
          <v-toolbar-title>Links</v-toolbar-title>
        </v-toolbar>
        <v-list two-line>
          <v-list-tile
            v-for="(item, index) in links"
            :key="index"
            @click="openUrl(item.url)"
            >
            <v-list-tile-action>
              <v-icon>collections_bookmark</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>{{item.title}}</v-list-tile-title>
              <v-list-tile-sub-title>{{item.description}}</v-list-tile-sub-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  import links from '../assets/json/links.json'
  export default {
    data () {
      return {
        links: links
      }
    },
    methods: {
      openUrl: function (url) { window.open(url, '_blank') }
    }
  }
</script>
