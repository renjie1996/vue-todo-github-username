<template>
  <div id="app">
    <h1>Username - Checker</h1>
    <Search v-on:CheckUser="CheckUser"></Search>
    <Result :github="github"></Result>
  </div>
</template>

<script>
import Search from '@/components/Search.vue'
import Result from '@/components/Result.vue'
export default {
  name: 'app',
  data () {
    return {
      github: {
        state: ''
      }
    }
  },
  methods: {
    CheckUser (username) {
      // alert('ok')
      fetch('https://api.github.com/users/' + username)
        .then(response => response.json())
        .then(data => {
          if (data && 'id' in data) {
            this.github.state = 'Not Avaiable'
          } else {
            this.github.state = 'Avaiable'
          }
        })
      // this.$http.get(
      //   'https://api.github.com/users/',
      //   {
      //     client_id: 'f0b427e8cd9907dbc8b6',
      //     client_secret: '73f1b8643251a16462933c65cb23094b4ada0497'
      //   }
      // ).then(response => {
      //   console.log(response)
      //   this.github.state = 'Not Avaiable'
      // }, response => {
      //   if (response.statusText === 'Not Found') {
      //     this.github.state = 'Avaiable'
      //   }
      // })
    }
  },
  created () {
    this.github.state = 'Search Waiting'
  },
  components: {
    Search,
    Result
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
