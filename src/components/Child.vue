<script setup>
import { ref } from 'vue';

const props = defineProps(['item'])
let emit = defineEmits(['addToCart'])

let amount = ref(0)

function addItemToCart() {
   let toCart = {...props.item}
   toCart.amount = amount.value 
   emit('addToCart', toCart)
}
</script>

<template>
    <div class="card">
        <h3>{{ item.name }}</h3>
        <p>{{ item.description }}</p>
        <p>Цена: <b>{{ item.price }}</b> </p>
        
        <input class="number2" type="number" v-model="amount">
        <button @click="addItemToCart" style="color: blue;">Купить</button>
    </div>
</template>

<style scoped>
.card {
    border: 1px solid black;
    width: 300px;
    aspect-ratio: 1;
    margin: 20px;
}

.number2 {
    color: rgb(255, 0, 0);
    background-color: black;
    height: 30px;
    width: 50px;
}
</style>