<template>
  <div class="search-form">
    Enter Username:
    <input type="text" placeholder="Enter UserName"
      v-model="username" @keypress.enter="checkUser">
    <button v-on:click="checkUser">Search</button>
  </div>
</template>

<script>
export default {
  name: 'search',
  data () {
    return {
      username: ''
    }
  },
  methods: {
    checkUser () {
      if (this.username === '') alert('you must enter username')
      else this.$emit('CheckUser', this.username)
    }
  }
}
</script>

<style>

</style>
