<script>
import PRODUCTS from "./products.json";

export default {
  data() {
    return {
      products: PRODUCTS,
      total: 0,
    };
  },

  computed: {
    sum() {
      let total = 0;
      this.products.forEach((item, i) => {
        total += item.price * item.quantity;
      });
      return total;
    }
  }
}
</script>

<template>
  <body>
    
    <nav class="nav-bar">
      <img src="../basicassets/dinaschoice.png" alt=""  class="web-logo">
      <div>
        <img src="../basicassets/usericon.png" alt="" width="100px">
        <img src="../basicassets/settingsicon.png" alt="" width="100px">
      </div>
    </nav>
      <article v-for="(product, index) of products" :key="product.uuid" class="products">
        <div>{{index}}</div>
      <div><img :src="product.image" :alt="product.name" width="150" /></div>
      <div>{{product.name}}</div>
      <div>{{product.price}}</div>
      <input type="number" v-model="product.quantity" placeholder="0" />
      <div>{{product.quantity * product.price}}</div>
      </article>
    

    <div></div>
    <div></div>
    <div></div>

    <footer></footer>

  </body>
</template>

<style scoped>
body {
  margin: 0;
  padding: 0;
}

.nav-bar {
  display: flex;
  justify-content: space-between;
}

.web-logo {
  width: 20%;
}

.products {
  display: flex;
  justify-content: space-around;
}
</style>
