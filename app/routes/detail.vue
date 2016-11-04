<template lang="html">
  <div class="">
    <div class="detail__head">
      <h1 class="title">{{puppy.name}}</h1>
      <button class="danger" @click="removePuppy">Remove Puppy</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ['apiUrl'],

  data() {
    return {
      id: this.$route.params.id,
      puppy: {},
    };
  },

  mounted() {
    this.loadData();
  },

  watch: {
    // call again the method if the route changes
    '$route': 'loadData',
  },

  methods: {
    loadData() {
      fetch(`${this.apiUrl}/${this.$route.params.id}`)
        .then((r) => r.json())
        .then((puppy) => {
          this.puppy = puppy;
        })
        .catch(() => {
          this.$router.push({
            name: 'index'
          });
        });
    },
    removePuppy() {
      if (confirm('Are you sure?')) {
        this.$emit('delete', this.puppy);
      }
    },
  },
};
</script>
