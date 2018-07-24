<template>
  <div>
    <h1>User Edit</h1>
    <button @click='editAge'> Edit Age </button>
    Age: {{ usrAge }}
  </div>
</template>

<script>
  import { eventbus } from '../main.js';

  export default {
    props: ['usrAge'],
    methods: {
      editAge: function(){
        this.usrAge = 30
        eventbus.$emit('updatedAge', this.usrAge)
      }
    }
  }
</script>

<style>
</style>
