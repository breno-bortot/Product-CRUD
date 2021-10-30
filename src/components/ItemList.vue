<template>
  <div class="table-active">
    <!-- <tr>
      <th scope="row">Active</th>
      <td>Column content</td>
      <td>Column content</td>
      <td>Column content</td>
    </tr> -->
    <!-- <li
      class="list-group-item d-flex justify-content-between align-items-center"
    >
      <span>{{ product.id }}</span>
      <span>{{ product.name }}</span>
      <span>{{ product.price }}</span>class="badge bg-primary rounded-pill">
      <span class="badge bg-primary rounded-pill">{{ product.stock }}</span>
    </li> -->
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