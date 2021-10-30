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
    async fetchProducts() {
      const res = await fetch("http://localhost:500/products");
      const data = await res.json();
      return data;
    },
    async fetchProduct() {
      const res = await fetch(`http://localhost:500/products/${id}`);
      const data = await res.json();
      return data;
    },
  },
  data() {
    return {
      products: [],
    };
  },
  async created() {
    this.products = await this.fetchProducts();
  },
};
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
