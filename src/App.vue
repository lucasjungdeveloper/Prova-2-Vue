<template>
  <div id="app">
    <Client :client="client"/>
    <br>
    
    <div v-for="product in products" :key="product.id">
      <Product :product="product"/>
    </div>
  </div>
</template>

<script>
import Client from './components/Client'
import Product from './components/Product'

export default {
  name: 'App',
  components: {
    Client,
    Product,
  },
  data() {
    return {
      client: {
        name: 'Lucas Jung',
        profession: 'Estudante',
      },
      products: [
      {
        id: '748fasdf74821as',
        price: 2400.5,
        name: 'Celular',
        description: 'Xiaomi MI9 - 8GB Ram | 124GB Armazenamento',
      },
        {
          id: '99iu12899dh2q3h',
          price: 3205,
          name: 'Notebook',
          description: 'Acer Aspire - 8GB Ram | 500GB Armazenamento',
        },
        {
          id: '8uafs9uh0q9382l',
          price: 40,
          name: 'Pendrive',
          description: 'Multilazer | 16GB Armazenamento',
        },
      ]
    }
  },
}
</script>

<style>
html {
  background-color: #222330;
  color: white;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
