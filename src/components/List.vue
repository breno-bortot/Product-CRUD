<template>
  <div class="card-body table-responsive-md">
    <table class="table table-hove">
      <thead>
        <tr class="table-dark">
          <th scope="col">#</th>
          <th scope="col">Name</th>
          <th scope="col">Price</th>
          <th class="border-end col-1" scope="col">Stock</th>
          <th class="col-1" scope="col">Action</th>
        </tr>
      </thead>
      <tbody>
        <tr :key="product.id" v-for="product in products" class="table-active">
          <th scope="row">{{ product.id }}</th>
          <td>{{ product.name }}</td>
          <td>$ {{ product.price.toFixed(2) }}</td>
          <td class="badge rounded-pill bg-success float-end me-3 mt-2">
            {{ product.stock }}
          </td>
          <td>
            <div class="d-flex justify-content-evenly">
              <button
                type="button"
                class="btn btn-outline-warning mx-1"
                data-bs-toggle="modal"
                data-bs-target="#exampleModal"
              >
                Edit
              </button>
              <button type="button" class="btn btn-outline-danger mx-1">
                Delete
              </button>
            </div>
          </td>
        </tr>
      </tbody>
    </table>
    <!-- <ul :key="product.id" v-for="product in products" class="list-group">
      <ItemList :product="product" />
    </ul> -->
  </div>
</template>
<script>
import ItemList from "./ItemList.vue";
export default {
  name: "List",
  props: {
    products: Array,
  },
  components: {
    ItemList,
  },
};
</script>
<style scoped>
.table > :not(caption) > * > * {
  padding: 1.5rem 1.5rem !important;
}
</style>