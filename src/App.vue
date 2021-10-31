<template>
  <div class="container">
    <div class="card border-dark mb-3">
      <Header
        @do-add="doAdd"
        @search-submit="filterAction"
        title="Product CRUD"
      />
      <Modal
        :product="product"
        :editing="editing"
        @add-product="addProduct"
        @edit-product="editProduct"
      />
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
      product: {},
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
    async doEdit(id) {
      this.product = await this.fetchProduct(id);
      this.editing = true;
    },
    async editProduct(editedProduct) {
      const res = await fetch(
        `http://localhost:500/products/${editedProduct.id}`,
        {
          method: "PUT",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify(editedProduct),
        }
      );

      const data = await res.json();

      this.products = this.products.map((product) =>
        product.id === editedProduct.id ? data : product
      );
    },
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
    async fetchProduct(id) {
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
