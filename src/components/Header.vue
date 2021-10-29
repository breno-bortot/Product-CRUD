<template>
  <div class="card-header">
    <Button />
    <h1>{{ title }}</h1>
    <SearchBar  @search-submit="getSearchInput"/>
  </div>
</template>
<script>
import Button from "./Button.vue";
import SearchBar from "./SearchBar.vue";

export default {
  name: "Header",
  props: {
    title: String,
  },
  components: {
    Button,
    SearchBar
  },
  emits: ['search-submit'],
  methods: {
     getSearchInput(searchInput) {
         this.$emit('search-submit', searchInput)
     }
  }
};
   
</script>
<style>
</style>