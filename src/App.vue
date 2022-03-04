<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src="/images/logo.png">
      </router-link>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item browse">
          <img src="/images/globe.png">
          <p>Browse</p>
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <img src="/images/love.png">
          <p>{{ numberOfItems }} items</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
  <div style="margin: 100px;"></div>
   <div class="footer" style="height: 200px; width: 100%; background-color: gray; display: flex; justify-content: center; align-items: center;">      
      <div class="link">
        <a href="https://github.com/nathanctodd/GroceryStore" class="githublink" style="display: flex; font-size: 30px; color: white;">Nathan Todd  |  GitHub  |  Grocery Store</a>
      </div>
    </div>
</div>
</template>



<script>
  export default {
    computed: {
      numberOfItems() {
        console.log(this.$root.$data.cart);       
        return this.$root.$data.cart.length;
      }
    }
  }

</script>


<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;

}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu a {
  color: #B84901;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}
</style>
