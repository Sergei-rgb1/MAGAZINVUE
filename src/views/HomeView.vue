<script setup>
import { reactive } from 'vue'
import Child from "../components/Child.vue"
let goods = reactive([
    {
        name: "Колбаса",
        description: "Вареная с кусками мяса",
        price: 2000,
        amount:0
    },
    {
        name: "Хлеб",
        description: "Высший сорт",
        price: 100,
        amount:0
    },
]
)
let cart = reactive(
    []
)
function addToCart(item) {
    if (!cart.length) {
    cart.push (item)
}else {
    for (let i = 0; i < cart.length; i++) {
        console.log(cart[i].name)
        console.log(item.name);
        
       if (cart[i].name==item.name) {
        cart[item].amount=cart[item].amount+item.amount
       } else {
        cart.push.item
       }
       
    }
}

}


</script>

<template>
    <h2>Витрина товаров</h2>
<div class="wrapper">
    <Child v-for="item in goods" :item="item" @addToCart="addToCart">
    </Child>
</div>
{{ cart }}
</template>

<style scoped>
.wrapper {
    display: flex;
    flex-wrap: wrap;
}
</style>