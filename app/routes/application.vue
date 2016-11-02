<template lang="html">
  <div class="app">
    <nav class="nav">
    <div class="nav-left">
      <router-link :to="{ name: 'index' }" class="nav-item is-brand">Puppies</router-link>
    </div>

    <div class="nav-center">

      <router-link :to="{ name: 'index' }" class="nav-item">All Puppies</router-link>

      <router-link :to="{ name: 'new' }" class="nav-item">Add Puppy</router-link>
    </div>
  </div>
</template>

<script>
import IndexPage from './index.vue'
export default {
  data() {
    return {
    };
  },

  methods: {

  },
};
</script>
