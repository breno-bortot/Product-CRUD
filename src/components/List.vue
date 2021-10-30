<template>
  <div class="card-body">
    <table class="table table-hover">
      <thead>
        <tr class="table-dark">
          <th scope="col">#</th>
          <th scope="col">Name</th>
          <th scope="col">Price $</th>
          <th class="text-end" scope="col">Stock</th>
        </tr>
      </thead>
      <tbody>
        <tr :key="product.id" v-for="product in products" class="table-active">
          <th scope="row">{{ product.id }}</th>
          <td>{{ product.name }}</td>
          <td>{{ product.price.toFixed(2) }}</td>
          <td class="badge bg-success float-end mt-1 me-2">
            {{ product.stock }}
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
<style>
</style>