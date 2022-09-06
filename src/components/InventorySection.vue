<template>
    <div>
      <div class="row">
        <div v-for="(item, index) in items" :key="index" class="card" style="width: 13rem;">
   <img :src="item.photo" alt="...">
   <div class="card-body">
     <h5 class="card-title">{{item.title}}</h5>
     <p class="card-text">{{item.price}}</p>
     <a @click="addToCart(item)" class="btn btn-primary">+Add</a>
   </div>
 </div>
  
 
    </div> 
    </div>
</template>
<script>
export default {
    props:['items'],
    methods:{
      addToCart(item){
        this.$emit('newItemAdded', item)
        console.log(item)
      }
    }
}
</script>
<style>
    
</style>