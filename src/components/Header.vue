<template>
  <div class="card-header">
    <Button />
    <h1>{{ title }}</h1>

    <div class="container">
      <div class="form-group row">
        <label for="search" class="col-sm-2 col-form-label">Search</label>
        <div class="col-sm-10">
          <input
            type="text"
            class="form-control"
            id="search"
            v-model="search"
            placeholder="search here"
          />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Button from "./Button.vue";

export default {
  name: "Header",
  props: {
    title: String,
  },
  components: {
    Button,
  },
  data() {
    return {
      searchInput: "",
    };
  },
};
</script>
<style>
</style>