<template >
  <div>
    <div
      class="modal"
      id="exampleModal"
      tabindex="-1"
      aria-labelledby="exampleModalLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h5 v-if="!editing" class="modal-title text-success">
              Add Product
            </h5>
            <h5 v-else class="modal-title text-warning">Edit Product</h5>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="modal"
              aria-label="Close"
            >
              <span aria-hidden="true"></span>
            </button>
          </div>

          <Form
            :product="product"
            :editing="editing"
            @add-product="addProduct"
            @edit-product="editProduct"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Form from "./Form.vue";
export default {
  name: "Modal",
  props: {
    editing: Boolean,
    product: Object,
  },
  components: {
    Form,
  },
  emits: ["add-product", "edit-product"],
  methods: {
    addProduct(newProduct) {
      this.$emit("add-product", newProduct);
    },
    editProduct(editedProduct) {
      this.$emit("edit-product", editedProduct);
    },
  },
};
</script>
<style>
</style>