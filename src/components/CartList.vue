


<template>
<div class="wrapper">
  <div class="products" v-if="getCartLength != 0">
    <div class="product" v-for="product in getCart" :key="product.id">
      <div class="info">
        <h1>{{product.name}}</h1>
        <p>{{product.country}}</p>
      </div>
      <div class="image">
        <img :src="'/images/products/'+product.image">
      </div>
      <div class="price">
        <h2>{{product.price}}</h2>
        <button v-on:click="removeFromCart(product)" class="auto">Remove from Cart</button>
      </div>
    </div>
  </div>
  <div v-else>
      <p>Cart is Empty!</p>
  </div>
</div>
</template>

<script>
export default {
  name: 'CartList',
  props: {
    cart: Array,
  },
  computed: {
      getCart() {
          return this.$root.$data.cart;
      },
      getCartLength() {
          return this.$root.$data.cart.length;
      }
  },
   methods: { 
    removeFromCart(product) {
      var index = this.$root.$data.cart.indexOf(product);
      this.$root.$data.cart.splice(index, 1);
    }
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.products {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.product {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}

.product img {
  border: 2px solid #333;
  height: 150px;
  width: 200px;
  object-fit: cover;
}

.product .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #1f86c2;
  color: #000;
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 20px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}


.price {
  display: flex;
}

.price h2 {
    padding: 10px;
    margin: 10px;
}

button {
  height: 50px;
  background: #000;
  color: white;
  border: none;
  padding: 10px;
    margin: 10px;

}

.auto {
  margin-left: auto;
}

p {
    margin: 100px;
    padding: 100px;
    font-size: 30px;
}

</style>