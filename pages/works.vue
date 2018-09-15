<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <v-toolbar>
        <v-toolbar-title>Books</v-toolbar-title>
      </v-toolbar>
      <v-container fluid grid-list-md>
        <v-layout row wrap>
          <v-flex xs12 sm12 md4
                  v-for="(book, index) in books"
                  :key="index"
                  >
            <v-card>
              <v-card-title primary-title>
                <div class="headline">{{book.title}}</div>
                <div>{{book.description}}</div>
              </v-card-title>
              <v-card-text>
                <div>{{book.publisher}} ({{book.date}})</div>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn :href=book.amazon target="_blank">
                  <v-icon>{{book.icon}}</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </v-flex>
    <v-flex xs12 sm8 md6>
      <v-toolbar>
        <v-toolbar-title>Works</v-toolbar-title>
      </v-toolbar>
      <v-container fluid grid-list-md>
        <v-layout row wrap>
          <v-flex xs12 sm12 md4
                  v-for="(work, index) in works"
                  :key="index"
                  >
            <v-card>
              <v-card-title primary-title>
                <div class="headline">{{work.title}}</div>
              </v-card-title>
              <v-card-text>
                <div>{{work.publisher}} ({{work.date}})</div>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn :href=work.url target="_blank">
                  <v-icon>visibility</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </v-flex>
  </v-layout>
</template>

<script>
  import books from '../assets/json/books.json'
  import works from '../assets/json/works.json'
  export default {
    data () {
      return {
        works: works,
        books: books
      }
    },
    methods: {
      openUrl: function (url) { window.open(url, '_blank') }
    }
  }
</script>
