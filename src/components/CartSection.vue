<template>
    <div>
        <ul class="list-group">
            <li class="list-group-item">
              <span>Name</span>
              <span class="item-price float-right">Price</span>
            </li>
           <hr>
           <li class="list-group-item" v-for="(item, index) in items" :key="index">
              <span class="item-name">{{item.title}}</span>
              <span class="item-price float-right">{{item.price}}</span>
              
          </li>
          <hr>
          <li> Total{{totalPrice}}</li>
          </ul>
    </div>
</template>
<script>
export default {
    props:['items'],
    computed: {
     totalPrice(){
        let total = 0
        this.items.forEach(item => {
            total += parseFloat(item.price);
          });
          return total;
     }
     
    }
}
</script>
<style>
    
</style>