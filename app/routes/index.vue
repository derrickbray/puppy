<template lang="html">
  <div class="">
    <a class="button is-primary is-pulled-right">Add a Pupper</a>
  <table class="table">
    <thead>
      <tr>
        <th>Name</th>
        <th>Age</th>
    </tr>
    <tbody>
      <tr v-for="item in lunchSpots">
        <td>{{ puppy.name }}</td>
        <td>{{ puppy.age }}</td>
        <td>
          <router-link :to="{ name: 'detail', params: {id:puppy.id} }">Read More</router-link>
        </td>
      </tr>
    </tbody>
  </thead>
  </div>
</template>

<script>
export default {
  data() {
    return {
    };
  },

  methods: {

  },
};
</script>
