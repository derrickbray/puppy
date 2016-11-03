<template lang="html">
  <div class="">
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
  <textarea class="textarea" placeholder="Textarea"></textarea>
</p>

<p class="control">
  <button class="button is-link">Cancel</button>
  <button class="button is-primary">Submit</button>
</p>
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
