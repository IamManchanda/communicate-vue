<template>
  <div class="component">
    <h3>You may edit the User here</h3>
    <p>Edit me!</p>
    <p>User Name : {{ name }} </p>
    <p>User Age: {{ age }} </p>
    <button class="btn btn-primary" @click="editAge">Edit Age</button>
  </div>
</template>

<script>
  import { eventBus } from '../main';
  export default {
    props: {
      name: { type: String },
      age: { type: Number }
    },
    methods: {
      editAge() {
        this.age = 24;
        eventBus.changeAge(this.age);
      }
    }
  }
</script>

<style scoped lang="scss">
  div {
    background-color: lightgreen;
  }
</style>
