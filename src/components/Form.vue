<template>
  <div>
    <form>
      <fieldset>
        <div class="form-group row">
          <label for="productName" class="col-sm-2 col-form-label">Name</label>
          <div class="col-sm-10">
            <input
              type="text"
              class="form-control"
              id="productName"
              v-model="name"
              placeholder="Enter name"
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
              type="number"
              class="form-control"
              id="productStock"
              v-model="name"
              placeholder="Enter stock"
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
              type="number"
              class="form-control"
              id="productPrice"
              v-model="name"
              placeholder="Enter price"
            />
          </div>
        </div>
      </fieldset>
    </form>
  </div>
</template>
<script>
export default {
  name: "Form",
  data() {
    return {
      name: "",
      price: "",
    };
  },
};
</script>
<style>
</style>