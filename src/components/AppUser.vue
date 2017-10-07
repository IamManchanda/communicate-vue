<template>
  <div class="component">
    <h1>The User Component</h1>
    <p>I'm an awesome User!</p>
    <p>Name: {{ name }} </p>
    <p>Age: {{ age }} </p>
    <button class="btn btn-primary" @click="changeName">Change my Name</button>
    <hr>
    <div class="row">
      <div class="col-12 col-sm-6">
        <app-user-detail :name="name" :age="age" @nameWasReset="name = $event"></app-user-detail>
      </div>
      <div class="col-12 col-sm-6">
        <app-user-edit :name="name" :age="age"></app-user-edit>
      </div>
    </div>
  </div>
</template>

<script>
  import AppUserDetail from './AppUserDetail.vue';
  import AppUserEdit from './AppUserEdit.vue';

  export default {
    data() {
      return {
        name: 'Harry',
        age: 25
      };
    },
    methods: {
      changeName() {
        this.name = 'Anna';
      }
    },
    components: { AppUserDetail, AppUserEdit }
  }
</script>

<style scoped lang="scss">
  div {
    background-color: lightblue;
  }
  .btn-primary {
    cursor: pointer;
  }
</style>
