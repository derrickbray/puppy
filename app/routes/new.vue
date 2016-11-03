<template lang="html">
  <div class="">

    <form @submit.prevent="saveForm">

    <label class="label">Name</label>
      <p class="control">
        <input class="input" type="text">
      </p>

    <label class="label">Age</label>
      <p class="control ">
        <input class="input" type="text" >
      </p>

    <label class="label">Sex</label>
      <p class="control">
        <span class="select">
          <select>
            <option>Select dropdown</option>
            <option>Female</option>
            <option>Male</option>
          </select>
        </span>
      </p>

    <label class="label">Color</label>
      <p class="control">
        <input class="input" type="text" >
      </p>

    <label class="label">Breed</label>
      <p class="control">
        <input class="input" type="text" >
      </p>

    <label class="label">Image URL</label>
      <p class="control">
        <input class="input" type="text" >
      </p>

    <label class="label">Description</label>
      <p class="control">
        <textarea class="textarea"></textarea>
      </p>

      <p class="control">
        <router-link :to="{name: 'index'}" class="button is-primary is-outlined">Cancel</router-link>
        <button class="button is-primary">Submit</button>
      </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      formValues: {
      name: '',
      age: '',
      sex: '',
      color: '',
      breed: '',
      image_url: '',
      description: '',
    }
    };
  },

  methods: {
    saveForm() {
    this.$emit('addPuppy', this.formValues);
  },
  },
};
</script>
