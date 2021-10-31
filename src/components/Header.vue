<template>
  <div class="card-header">
    <button
      type="button"
      class="btn btn-primary float-end mt-2"
      data-bs-toggle="modal"
      data-bs-target="#exampleModal"
    >
      Add Product
    </button>
    <Modal @add-product="addProduct" />
    <h1>{{ title }}</h1>
    <SearchBar @search-submit="getSearchInput" />
  </div>
</template>
<script>
import Modal from "./Modal.vue";
import SearchBar from "./SearchBar.vue";

export default {
  name: "Header",
  props: {
    title: String,
  },
  components: {
    Modal,
    SearchBar,
  },
  emits: ["search-submit", "add-product"],
  methods: {
    getSearchInput(searchInput) {
      this.$emit("search-submit", searchInput);
    },
    addProduct(newProduct) {
      this.$emit("add-product", newProduct);
    },
  },
};
</script>
<style>
</style>