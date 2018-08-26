<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <v-card>
        <v-card-media
          src="/Me_2016.jpg"
          height="350px"
          >
          <v-layout
            column
            fill-height
            >
            <v-spacer></v-spacer>
            <v-card-title class="white--text pl-5 pt-5">
              <div class="display-1 pl-5 pt-5">Yoshiyasu SAEKI</div>
            </v-card-title>
          </v-layout>
        </v-card-media>
        <v-list two-line>
          <v-list-tile
            v-for="(item, index) in profiles"
            :key="index"
            >
            <v-list-tile-action>
              <v-icon>{{item.icon}}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>{{item.value}}</v-list-tile-title>
            <v-list-tile-sub-title>{{item.key}}</v-list-tile-sub-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  export default {
    data () {
      return {
        profiles: [
          {key: 'Name (Japanese)', icon: 'face', value: '佐伯 嘉康'},
          {key: 'Nickname', icon: 'account_circle', value: 'laclefyoshi'},
          {key: 'E-mail', icon: 'contact_mail', value: 'contact [at] saekiyoshiyasu.org'},
          {key: 'Birthday', icon: 'event', value: 'October 1983'},
          {key: 'Birthplace', icon: 'place', value: 'Toyooka, Hyogo, Japan'},
          {key: 'Workplace', icon: 'place', value: 'Tokyo, Japan'}
        ]
      }
    }
  }
</script>
