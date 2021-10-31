<template>
  <div class="modal-body">
    <form @submit="onSubmit">
      {{ product }}
      <fieldset>
        <div class="form-group row">
          <label for="productName" class="col-sm-2 col-form-label">Name</label>
          <div class="col-sm-10">
            <input
              v-if="!editing"
              type="text"
              class="form-control"
              id="productName"
              v-model="name"
              placeholder="Enter name"
            />
            <input
              v-else
              type="text"
              class="form-control"
              id="productName"
              v-model="product.name"
            />
          </div>
        </div>
        <br />
        <div class="form-group row">
          <label for="productStock" class="col-sm-2 col-form-label"
            >Stock</label
          >
          <div class="col-sm-10">
            <input
              v-if="!editing"
              type="number"
              class="form-control"
              id="productStock"
              v-model="stock"
              placeholder="0"
              min="0"
            />
            <input
              v-else
              type="number"
              class="form-control"
              id="productStock"
              v-model="product.stock"
              min="0"
            />
          </div>
        </div>
        <br />
        <div class="form-group row">
          <div class="input-group mb-3">
            <label for="productPrice" class="col-sm-2 col-form-label"
              >Price
            </label>
            <span class="input-group-text">$</span>
            <input
              v-if="!editing"
              type="number"
              class="form-control"
              id="productPrice"
              v-model="price"
              placeholder="0"
              min="0"
            />
            <input
              v-else
              type="number"
              class="form-control"
              id="productPrice"
              v-model="product.price"
              min="0"
            />
          </div>
        </div>
      </fieldset>
      <div class="modal-footer">
        <button v-if="!editing" type="submit" class="btn btn-success">
          Add
        </button>
        <button v-else type="submit" class="btn btn-warning">Edit</button>
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">
          Close
        </button>
      </div>
    </form>
  </div>
</template>
<script>
export default {
  name: "Form",
  data() {
    return {
      name: "",
      stock: "",
      price: "",
    };
  },
  props: {
    editing: Boolean,
    product: Object,
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();

      if (!this.editing) {
        if (!this.name && !this.stock && !this.price) {
          alert("Please fill in all fields");
          return;
        }

        const newProduct = {
          //   id: Math.floor(Math.random() * 100000),
          name: this.name,
          stock: this.stock,
          price: this.price,
        };
        this.$emit("add-product", newProduct);

        this.name = "";
        this.stock = "";
        this.price = "";
      } else {
        this.$emit("edit-product", this.product);
      }
    },
  },
};
</script>
<style>
</style>