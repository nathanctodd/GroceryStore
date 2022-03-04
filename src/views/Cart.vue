<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <h1>Cart</h1>
  </div>
  <CartList :products="products" />
</div>
</template>

<script>
import CartList from "../components/CartList.vue"
export default {
  name: 'CartListObject',
  components: {
    CartList
  },
  computed: {
    products() {
        console.log(this.$root.$data.cart);
        //console.log()
      return this.$root.$data.cart;
    }
  },
  methods: {
    
  }
}
</script>

<style>

h1 {
    font-size: 70px;
}

</style>