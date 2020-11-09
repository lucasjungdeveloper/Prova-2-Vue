<template>
  <div id="app">
    <User />
    <h1>Promoções</h1>
    <br />

    <div v-for="product in products" :key="product.id">
      <Product :product="product" @removeProduct="removeProduct($event)" />
    </div>
  </div>
</template>

<script>
import User from "./components/User";
import Product from "./components/Product";

export default {
  name: "App",
  components: {
    User,
    Product,
  },
  data() {
    return {
      products: [
        {
          id: "748fasdf74821as",
          price: 4349.94,
          name: "Celular",
          description: "Xiaomi MI9 - GB Ram | 128GB Armazenamento",
          quantityAvailable: 23,
        },
        {
          id: "99iu12899dh2q3h",
          price: 3899,
          name: "Notebook",
          description: "Acer Aspire - 8GB Ram | 256GB SSD",
          quantityAvailable: 0,
        },
        {
          id: "8uafs9uh0q9382l",
          price: 25.29,
          name: "Pendrive",
          description: "Multilazer | 16GB Armazenamento",
          quantityAvailable: 34,
        },
      ],
    };
  },
  methods: {
    removeProduct: function($event) {
      const id = $event.id;
      this.products = this.products.filter((product) => product.id != id);
    },
  },
};
</script>

<style>
hr {
  height: 1px;
  background-color: slategrey;
  border: none;
}
html {
  background-color: #222330;
  color: white;
  overflow-x: hidden;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
