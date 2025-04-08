<script setup>
import { reactive } from 'vue'
import Child from "../components/Child.vue"
let goods = reactive([
    {
        name: "Колбаса",
        description: "Вареная с кусками мяса",
        price: 2000
    },
    {
        name: "Хлеб",
        description: "Высший сорт",
        price: 100
    },

]
)
let cart = reactive(
    []
)
function addToCart(item) {
    cart.push(item)

}
</script>

<template>
    <h2>Витрина товаров</h2>
<div class="wrapper">
    <Child v-for="item in goods" :item = 'item' @add-to-cart="">
    
    </Child>
</div>

</template>

<style scoped>
.wrapper {
    display: flex;
    flex-wrap: wrap;
}

</style>