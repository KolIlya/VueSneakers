<template>
    <div class="flex flex-col gap-2">
        <CartItem 
            image-url="/sneakers/sneakers-1.webp"
            title="Nike Blazer"
            :price="1205"
        />
        <CartItem 
            image-url="/sneakers/sneakers-1.webp"
            title="Nike Blazer"
            :price="1205"
        />
        <CartItem 
            image-url="/sneakers/sneakers-1.webp"
            title="Nike Blazer"
            :price="1205"
        />
    </div>
</template>

<script setup lang="ts">
import CartItem from './CartItem.vue'
</script>