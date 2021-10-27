<template>
   <div class="card-header">
      <h1>{{ title }}</h1>
      <input type="text" name="search" v-model="searchInput">
      <AddBtn />
   </div>
</template>
<script>
import AddBtn from './AddBtn.vue'

export default {
   name: "Header",
   props: {
      title: String,
   },
   components: {
      AddBtn,
   },
   data() {
      return {
         searchInput: ''
      }  
   }
}
</script>
<style>
   
</style>