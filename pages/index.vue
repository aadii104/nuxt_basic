<template>
  <v-container fluid>

    <v-layout row wrap>
      <v-flex xs12 sm6 md3>
        <v-card dark tile flat color="red darken-2">
          <v-card-text>
            <v-btn color="primary" v-on:click="call1('comments')">Comments</v-btn>
          </v-card-text>
          <v-list two-line>
            <v-list-tile-content>
              <ul id="example-1">
                <li v-for="x in box1">
                  {{ x.email }}
                </li>
              </ul>

            </v-list-tile-content>

          </v-list>
        </v-card>
      </v-flex>
      <v-flex xs12 sm6 md3>
        <v-card dark tile flat color="deep-orange lighten-1">
          <v-card-text>
            <v-btn color="primary" v-on:click="call2('posts')">posts</v-btn>
          </v-card-text>
          <v-list two-line>
            <v-list-tile-content>
              <ul id="example-1">
                <li v-for="x in box2">
                  {{ x.id }}
                </li>
              </ul>
            </v-list-tile-content>
          </v-list>
        </v-card>
      </v-flex>
      <v-flex xs12 sm6 md3>
        <v-card dark tile flat color="deep-orange darken-3">
          <v-card-text>
            <v-btn color="primary" v-on:click="call3('todos')">todos</v-btn>
          </v-card-text>
          <v-list two-line>
            <v-list-tile-content>
              <ul id="example-1">
                <li v-for="x in box3">
                  {{ x.title }}
                </li>
              </ul>
            </v-list-tile-content>

          </v-list>
        </v-card>
      </v-flex>
      <v-flex xs12 sm6 md3>
        <v-card dark tile flat color="deep-orange">
          <v-card-text>
            <v-btn color="primary" v-on:click="call4('users')">User</v-btn>
          </v-card-text>
          <v-list two-line>
            <v-list-tile-content>
              <ul id="example-1">
                <li v-for="x in box4">
                  {{ x.name }}
                </li>
              </ul>
            </v-list-tile-content>

          </v-list>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  import axios from 'axios'
  export default {
    data() {
      return {
        box1: [],
        box2: [],
        box3: [],
        box4: []
      }
    },
    // methods: {

    // },
    methods: {
      call1: function (value) {
        axios.get('https://jsonplaceholder.typicode.com/' + value).then(response => {
          this.box1 = response.data
          console.log(this.box)
        }).catch(e => {
          this.error.push(e);
        })
      },

      call2: function (value) {
        axios.get('https://jsonplaceholder.typicode.com/' + value).then(response => {
          this.box2 = response.data
          console.log(this.box)
        }).catch(e => {
          this.error.push(e);
        })
      },

      call3: function (value) {
        axios.get('https://jsonplaceholder.typicode.com/' + value).then(response => {
          this.box3 = response.data
          console.log(this.box)
        }).catch(e => {
          this.error.push(e);
        })
      },

      call4: function (value) {
        axios.get('https://jsonplaceholder.typicode.com/' + value).then(response => {
          this.box4 = response.data
          console.log(this.box4)
        }).catch(e => {
          this.error.push(e);
        })
      }
    }
  }
</script>