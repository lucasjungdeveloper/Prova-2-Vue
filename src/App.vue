<template>
  <div id="app">
    <Client/>
    <br>
    <Product :value="xiaomiMi9price"/>
  </div>
</template>

<script>
import Client from './components/Client'
import Product from './components/Product'

export default {
  name: 'App',
  data() {
    return {
      xiaomiMi9price: 2430.5
    }
  },
  components: {
    Client,
    Product,
  }
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
