<template lang="html">
  <div class="">
    <a class="button is-primary is-pulled-right">Add a Pupper</a>
    <h1 class="title">Puppies for Adoption</h1>
    <table  class="table">
      <thead>
        <tr>
          <th>Name</th>
          <th>Age</th>
          <th></th>
        </tr>
      </thead>
      <tbody>
        <tr v-if="puppy.adopted" v-for="puppy in puppies">
          <td>{{ puppy.name }}</td>
          <td>{{ puppy.age }}</td>
          <td>
            <router-link :to="{ name: 'detail', params: {id:puppy.id} }">Read More</router-link>
          </td>
        </tr>
      </tbody>
    </table>
</div>
</template>

<script>
export default {
  props: ['puppies'],

  data() {
    return {};
  },

  methods: {

  },
};
</script>
