<template>
  <div class="component">
    <h3>You may view the User Details here</h3>
    <p>Many Details</p>
    <p>User Name: {{ name }} </p>
    <p>User Age: {{ age }} </p>
    <button class="btn btn-primary" @click="resetName">Reset Name</button>
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
      resetName() {
        this.name = 'Harry'; 
        this.$emit('nameWasReset', this.name);
      }
    },
    created() {
      eventBus.$on('ageWasEdited', (age) => {
        this.age = age;
      });
    }
  }
</script>

<style scoped lang="scss">
  div {
    background-color: lightcoral;
  }
</style>
