<template lang="html">
  <div class="">
    <div class="detail__head">
      <h1 class="title">{{puppy.name}}</h1>

    </div>
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

mounted() {
  this.loadData();
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
  },
};
</script>
