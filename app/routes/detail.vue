<template lang="html">
  <div class="">
    <div class="detail__head">
      <h1 class="title has-text-centered">{{ puppy.name }}</h1>
      <div class="has-text-centered">
        <button class="button is-danger" @click="removePuppy">Remove Puppy</button>
        <template v-if="puppy.adopted">
          <button class="button is-success">
            <span class="icon">
              <i class="fa fa-paw"></i>
            </span>
            <span>I'm Adopted</span>
          </button>
        </template>
        <template v-else>
          <button class="button is-primary" @click="adopt">
          <span class="icon">
            <i class="fa fa-paw"></i>
          </span>
          <span>Adopt me</span>
        </button>
        </template>
      </div>
      <div class="column is-half is-offset-3">
          <div class="card-image">
            <figure class="image is-4by3">
              <img :src="puppy.image_url" alt="">
            </figure>
          </div>
        </div>


                <nav class="level">
                  <div class="level-item">
                    <p class="heading">Age</p>
                    <p class="title">{{ puppy.age }}</p>
                  </div>
                  <div class="level-item has-text-centered">
                    <p class="heading">Breed</p>
                    <p class="title">{{ puppy.breed }}</p>
                  </div>
                  <div class="level-item has-text-centered">
                    <p class="heading">Color</p>
                    <p class="title">{{ puppy.color }}</p>
                  </div>
                  <div class="level-item has-text-centered">
                    <p class="heading">Sex</p>
                    <p class="title">{{ puppy.sex }}</p>
                  </div>
                </nav>


                <div class="content">
                  <p class="heading is-centered">About Me</p>
                  <p class="subtitle">{{ puppy.description }}</p>
                </div>

    </div>
  </div>
</template>

<script>
export default {
  props: ['apiUrl', 'puppies'],


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
        this.$emit('removePuppy', this.puppy);
      }
    },
    adopt() {
      this.$router.push({
        name: 'index'
      });
      this.$emit('updatePuppy', this.puppy.id, {
        adopted: true
      });
    },
  },
};
</script>
