<template>
<div class='component'>
  <h1> The User Component </h1> I am an awesome user
  <button @click="changeName"> Change me </button>
  <p> Name: {{ name }} </p>
  <user-detail
    :name='name'
    @emitNameProp="name = $event"
    :resetFn='resetName'
    :usrAge='age'>
  </user-detail>
  <user-edit
    :usrAge = 'age'
   ></user-edit>

</div>
</template>

<script>
import UserDetail from './UserDetail.vue'
import UserEdit from './UserEdit.vue'

export default {
  data: function() {
    return {
      name: 'Triveni',
      age: '27'
      // name: ['Triveni', 'Jiya']
    }
  },

  components: {
    userDetail: UserDetail,
    userEdit: UserEdit
  },

  methods: {
    changeName() {
      this.name = 'Jiya'
    },

    resetName() {
      this.name = 'Triveni'
    }
  }
}
</script>

<style>
div.component {
  border: 1px solid black;
  padding: 30px;
}
</style>
