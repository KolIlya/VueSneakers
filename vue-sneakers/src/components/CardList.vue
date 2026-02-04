<template>
  <div class="grid grid-cols-4 gap-5 ">
    <Card 
      imageUrl="/sneakers/sneakers-1.webp"
      title="Nike Blazer"
      :price="1205"
      :isFavorite="true"
      :isAdded="true"
      @add="handleAdd"
    />
    <Card 
      imageUrl="/sneakers/sneakers-1.webp"
      title="Nike Blazer"
      :price="1205"
      :isFavorite="false"
      :isAdded="false"
      @add="handleAdd"
    />
  </div>
</template>

<script setup lang="ts">
import Card from './Card.vue'

const handleAdd = () => {
  console.log('Добавил')
}
</script>