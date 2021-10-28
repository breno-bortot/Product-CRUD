<template>
   <div class="card-body">
      <ul class="list-group">
         <ItemList />
         <ItemList />
         <ItemList />
         <ItemList />
      </ul>
   </div>
</template>
<script>
import ItemList from './ItemList.vue'
export default {
   name: 'List',
   components: {
      ItemList
   }
}
</script>
<style>
   
</style>