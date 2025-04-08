<script setup>
defineProps(['item'])
defineEmits(['addToCart'])
</script>



<template>
    <div class="card">
        <h3>{{ item.name }}</h3>
        <p>{{ item.description }}</p>
        <p>Цена: <b>{{ item.price }}</b> </p>
        <button @click="$emit('addToCart')" style="color: blue;">Купить</button>
        
    </div>

</template>

<style scoped>
.card {
    border: 1px solid black;
    width: 300px;
    aspect-ratio: 1;
    margin: 20px;
}
</style>