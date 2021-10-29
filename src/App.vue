<template>
  <div class="container">
    <div class="card border-success mb-3">
      <Header @form-submit="addProduct" @search-submit="filterAction"  title="Product CRUD" />
      <List />
      <!-- <Footer /> -->
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import List from "./components/List.vue";

export default {
  name: "App",
  components: {
    Header,
    List,
  },
  methods: {
     filterAction(searchInput) {
        console.log(searchInput);
     },
     addProduct(data) {
        console.log(data.name)
     }
  }
};
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
