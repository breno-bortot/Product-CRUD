<template >
  <div class="float-end mt-2">
    <button
      type="button"
      class="btn btn-primary"
      data-bs-toggle="modal"
      data-bs-target="#exampleModal"
    >
      Add Product
    </button>
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
            <h5 class="modal-title">Add Product</h5>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="modal"
              aria-label="Close"
            >
              <span aria-hidden="true"></span>
            </button>
          </div>
          <div class="modal-body">
            <Form />
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-success">Add</button>
            <button
              type="button"
              class="btn btn-secondary"
              data-bs-dismiss="modal"
            >
              Close
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Form from "./Form.vue";
export default {
  name: "Button",
  components: {
    Form,
  },
};
</script>
<style>
</style>