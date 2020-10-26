<template>
    <div id="product">
        <h3>{{ product.name }}</h3>
        <p>
            {{ product.description }}
            <br>
            R${{ product.price }}
        </p>
        <br>
        Quantidade: <input type="number" v-model="ammount" id="ammount">
        <p v-if="ammount > 0">Total a pagar por esse produto: R${{ product.price * ammount }}</p>
        <p v-else><br></p> <!-- Para evitar que os produtos subam e desçam conforme a quantidade é alterada -->
    </div>
</template>

<script>
export default {
    data() {
        return {
            ammount: Number,
        }
    },
    props: {
        product: Object,
    }
}
</script>

<style>
#ammount {
    text-align: center;  
    width: 50px;
}
#product {
    margin-bottom: 60px;       
}

</style>