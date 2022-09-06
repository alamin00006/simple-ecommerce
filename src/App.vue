<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
 <div class="container">
<NavbarSection></NavbarSection>
<div class="row pt-5">
  <div class="col-lg-9">
    <InventorySection @newItemAdded="addCartItem" :items="items"></InventorySection>
     </div>

  <div class="col-lg-3">
  <CartSection :items="cart"></CartSection>
    </div>
</div>
 </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import NavbarSection from './components/NavbarSection.vue'
import CartSection from './components/CartSection.vue';
import InventorySection from './components/InventorySection.vue';
import data from './data'
export default {
  name: 'App',
  components: {
    NavbarSection,
    CartSection,
    InventorySection
  },
  data(){
    return{
      items:[],
      cart:[
        {
          id:1,
          title:'test',
          price:10.50
          
        }
      ]
    }
  },
  mounted(){
    this.items = data
  },
  methods:{
    addCartItem(item){
      this.cart.push(item)
    }
  }
}
</script>

<style>

</style>
