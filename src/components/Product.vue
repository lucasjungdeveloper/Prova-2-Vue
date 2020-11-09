<template>
  <div
    :class="{
      unavaiable: product.quantityAvailable == 0,
      product: product.quantityAvailable > 0,
    }"
  >
    <hr />
    <button id="removeProduct" @click="removeProduct">X</button>
    <h3>{{ product.name }}</h3>
    <p>
      {{ product.description }}
      <br />
      R${{ product.price }}
    </p>
    <br />
    <p>Disponível: {{ product.quantityAvailable }}</p>
    <div id="buy">
      Quantidade: <input type="number" v-model="ammount" id="ammount" />
      <br />

      <p v-if="ammount > 0">
        Total a pagar por esse produto: R${{ product.price * ammount }}
        <br />
        <button @click="addToCart">Adicionar ao Carrinho</button>
      </p>
      <p v-else></p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ammount: Number,
      cart: [],
    };
  },
  props: {
    product: Object,
  },
  methods: {
    addToCart: function() {
      if (this.product.quantityAvailable >= this.ammount) {
        this.product.quantityAvailable -= this.ammount;
        this.ammount = 0;
      } else {
        alert("Quantidade desejada maior que quantidade disponível!");
      }
    },
    removeProduct: function() {
      this.$emit("removeProduct", { id: this.product.id });
    },
  },
};
</script>

<style>
#buy button {
  padding: 2px 15px;
  margin: 20px;
  background-color: rgb(53, 255, 53);
  font-weight: bold;
  border: none;
}
.unavaiable #buy {
  display: none;
}
#ammount {
  text-align: center;
  width: 50px;
}
.product {
  margin-bottom: 60px;
}
#removeProduct {
  position: relative;
  left: 49vw;
  color: rgb(255, 255, 255);
  background-color: rgb(105, 0, 0);
  padding: 2.5px 4px;
  border: 1px rgb(255, 0, 0) solid;
  border-radius: 30%;
  cursor: pointer;
}
</style>
