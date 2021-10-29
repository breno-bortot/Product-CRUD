<template>
  <div>
   <div class="modal-body">
      <form @submit="$emit('form-submit', formData)">
         <fieldset>
         <div class="form-group row">
            <label for="productName" class="col-sm-2 col-form-label">Name</label>
            <div class="col-sm-10">
               <input
               type="text"
               class="form-control"
               id="productName"
               v-model="formData.name"
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
               v-model="formData.stock"
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
               v-model="formData.price"
               placeholder="Enter price"
               />
            </div>
         </div>
         </fieldset>
      </form>
         <div class="modal-footer">
               <button type="submit" class="btn btn-success">Add</button>
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
</template>
<script>
export default {
  name: "Form",
  data() {
    return {
      formData: {
         name: "",
         stock: "",
         price: "",
      }
      
    };
  },
};
</script>
<style>
</style>