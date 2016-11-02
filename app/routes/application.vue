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
  </nav>

      <div class="box">
        <article class="media">
          <div class="media-left">
            <figure class="image is-64x64">
              <img src="http://www.fillmurray.com/g/140/100" alt="Image">
            </figure>
          </div>
          <div class="media-content">
            <div class="content">
              <h1>Name</h1>
              <router-link :to="{ name: 'new' }" class="nav-item">Read More</router-link>
            </div>
          </div>
        </article>
      </div>

    <routerview
    :api-url="apiUrl"
    >
    </routerview>
  </div>
</template>

<script>
import IndexPage from './index.vue'
const apiUrl = 'http://tiy-tn-class-api-fall-16.herokuapp.com/puppies/ryan';
export default {
  data() {
    return {
      puppies: [],
      apiUrl,
    };
  },

  methods: {
    getData() {
    fetch(apiUrl)
      .then((r) => r.json())
      .then((puppies) => {
        this.puppies = puppies;
      });
    },
  },
};
</script>
