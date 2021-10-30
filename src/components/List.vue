<template>
  <div class="card-body">
    <ul :key="product.id" v-for="product in products" class="list-group">
      <ItemList :product="product" />
    </ul>
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