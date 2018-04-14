<template>
  <ion-app>
    <ion-page class="show-page">
      <ion-header>
        <ion-toolbar>
          <ion-title>
            Ionic Vue
          </ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content>
        <div>
          <img src="../assets/logo.png">
        </div>
        <ion-list>
          <ion-item v-for="user of users" v-bind:key="user.idx">
            <ion-label full>
              {{user.name}}
            </ion-label>
          </ion-item>
        </ion-list>
      </ion-content>
    </ion-page>
  </ion-app>
</template>

<script>

import axios from 'axios'
export default {
  name: 'Test',
  data () {
    return {
      users: []
    }
  },
  created () {
    axios.get('http://jsonplaceholder.typicode.com/users').then(response => (this.users = response.data))
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
