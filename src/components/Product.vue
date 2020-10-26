<template>
    <div>
        <h3>{{ product }}</h3>
        <p>
            {{ description }}
            <br>
            R${{ valor }}
        </p>
        <br>
        Quantidade: <input type="number" v-model="ammount" id="ammount" placeholder="Quantidade">
        <h2>Total a pagar: R${{ value * ammount }}</h2>
    </div>
</template>

<script>
export default {
    data() {
        return {
            ammount: 0,
            product: 'Celular',
            description: 'Xiaomi MI9 - 8GB Ram | 124GB Armazenamento',
        }
    },
    props: {
        value: Number,
    }
}
</script>

<style>
#ammount {
    text-align: center;  
    width: 50px;
}
::-webkit-input-placeholder {
   color: #202020;
}

:-moz-placeholder { /* Firefox 18- */
   color: #202020;  
}

::-moz-placeholder {  /* Firefox 19+ */
   color: #202020;  
}

:-ms-input-placeholder {  
   color: #202020;  
}

</style>