<template>
  <div id="app">
    <app-user> </app-user>
  </div>
</template>

<script>
  import User from './components/User.vue';

  export default {
    data () {
      return {
        msg: 'Welcome to Your Vue.js App'
      }
    },

    components: {
      appUser: User,
    }
  }
</script>

<style>

</style>
