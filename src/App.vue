<template>
  <div class="container">
    <div class="card border-dark mb-3">
      {{ editing }}
      <Header
        @do-add="doAdd"
        @search-submit="filterAction"
        title="Product CRUD"
      />
      <Modal :editing="editing" @add-product="addProduct" />
      <List @do-edit="doEdit" @delete="deleteProduct" :products="products" />
      <!-- <Footer /> -->
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import List from "./components/List.vue";
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Header,
    List,
    Modal,
  },
  data() {
    return {
      products: [],
      editing: false,
    };
  },
  async created() {
    this.products = await this.fetchProducts();
  },
  methods: {
    filterAction(searchInput) {
      console.log(searchInput);
    },
    doAdd() {
      this.editing = false;
    },
    async addProduct(newProduct) {
      const res = await fetch("http://localhost:500/products", {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify(newProduct),
      });

      const data = await res.json();

      this.products = [...this.products, data];
    },
    doEdit(id) {
      this.editing = true;
    },
    // editProduct(id) {
    //   console.log(id);
    // },
    async deleteProduct(id) {
      if (confirm("Are you sure?")) {
        const res = await fetch(`http://localhost:500/products/${id}`, {
          method: "DELETE",
        });

        if (res.status === 200) {
          this.products = this.products.filter((product) => product.id !== id);
        } else {
          alert("Error deleting product");
        }
      }
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
};
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
