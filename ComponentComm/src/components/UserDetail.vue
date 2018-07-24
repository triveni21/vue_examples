<template>
  <div>
    <h1>User Details</h1>
    <p>Name: {{ switchName() }} </p>
    <button @click="resetName">Reset me</button>
    <button @click="resetFn">Reset me (parent fun)</button>
    Age: {{ usrAge }}
    <hr></hr>
  </div>
</template>

<script>
  import { eventbus } from '../main.js';

  export default {
    //props: ['name'],
    props: {
            name: {
               type: String,
               default: 'VueJS'
               // default: function(){
               //  return ['Hi', 'Vue']
               //  }
                // default: ['Hi', 'Vue']
              },
              resetFn: Function,
              usrAge: Number
          },
    methods: {
      switchName() {
        return this.name.split('').reverse().join('')
        //return this.name
      },

      resetName(){
        this.name = 'Triveni'
        this.$emit('emitNameProp', this.name)
      }
    },

    created() {
      eventbus.$on('updatedAge', (data) => {
        this.usrAge = data
      });
    }
  }
</script>

<style>
</style>
