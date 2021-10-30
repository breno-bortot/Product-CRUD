<template>
  <div class="container">
    <div class="card border-success mb-3">
      <Header
        @form-submit="addProduct"
        @search-submit="filterAction"
        title="Product CRUD"
      />
      <List :products="products" />
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
      console.log(data.name);
    },
  },
  data() {
    return {
      products: [],
    };
  },
  created() {
    this.products = [
      { id: 1, name: "Embutido Cracóvia", stock: 5, price: 23 },
      { id: 2, name: "Salame Milano", stock: 15, price: 42 },
      { id: 3, name: "Mortadella", stock: 25, price: 12 },
    ];
  },
};
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
