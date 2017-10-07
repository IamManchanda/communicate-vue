<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <app-user></app-user>
      </div>
    </div>
  </div>
</template>

<script>
  import AppUser from './components/AppUser.vue';

  export default {
    components: { AppUser }
  }
</script>

<style lang="scss">
  body {
    padding-top: 2rem;
  }
  div.component {
    border: 1px solid black;
    padding: 30px;
  }
</style>
