<template lang="html">
  <div class="">

  </div>
</template>

<script>
export default {
  data() {
    return {
      id: this.$route.params.id,
      puppies: {},
    };
  },

  methods: {
    loadData() {
    fetch(`${this.apiUrl}/${this.id}`)
      .then((r) => r.json())
      .then((puppy) => {
        this.puppy = puppy;
      })
      .catch(() => {
        this.$router.push({name: 'index'});
      });
  },
};
</script>
