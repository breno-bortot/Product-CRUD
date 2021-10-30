<template>
  <div>
    <li
      class="list-group-item d-flex justify-content-between align-items-center"
    >
      <span>{{ product.id }}</span>
      <span>{{ product.name }}</span>
      <span>{{ product.stock }}</span>
      <span>{{ product.price }}</span>

      <span class="badge bg-primary rounded-pill">14</span>
    </li>
  </div>
</template>
<script>
export default {
  name: "ItemList",
  props: {
    product: Object,
  },
};
</script>
<style>
</style>