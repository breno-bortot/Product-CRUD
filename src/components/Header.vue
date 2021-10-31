<template>
  <div class="card-header">
    <button
      @click="$emit('do-Add')"
      type="button"
      class="btn btn-success float-end mt-2"
      data-bs-toggle="modal"
      data-bs-target="#exampleModal"
    >
      Add Product
    </button>
    <h1>{{ title }}</h1>
    <SearchBar @search-submit="getSearchInput" />
  </div>
</template>
<script>
import SearchBar from "./SearchBar.vue";

export default {
  name: "Header",
  props: {
    title: String,
  },
  components: {
    SearchBar,
  },
  emits: ["search-submit", "add-product"],
  methods: {
    getSearchInput(searchInput) {
      this.$emit("search-submit", searchInput);
    },
  },
};
</script>
<style>
</style>