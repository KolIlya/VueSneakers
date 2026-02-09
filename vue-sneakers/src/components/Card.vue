<template>
  <div class="card flex flex-col justify-between relative p-8 border rounded-xl cursor-pointer transition hover:-translate-y-1 hover:shadow-xl">
    <img 
      :src="isFavorite ? '/like-2.svg' : '/like-1.svg'" 
      alt="Like" 
      class="absolute top-8 left-8 cursor-pointer transition-transform hover:scale-110"
      :title="isFavorite ? 'Убрать из избранного' : 'Добавить в избранное'"
    />
    <img :src="imageUrl" alt="Sneaker" class="max-h-60 w-auto object-contain" />
    <span class="mt-2">{{title}}</span>

    <div class="flex justify-between items-center mt-5">
      <div class="flex flex-col">
        <span class="text-muted">Цена</span>
        <span>{{ price }} руб.</span>
      </div>

      <img 
        :src="isAdded ? '/checked.svg' : '/plus.svg'" 
        alt="Add" 
        class="cursor-pointer"
        :title="isAdded ? 'Убрать из корзины' : 'Добавить в корзину'"
        @click="$emit('add')" 
      />
    </div>
  </div>
</template>

<script setup lang="ts">

defineProps<{
  imageUrl: string,
  title: string,
  price: number,
  isFavorite: boolean,
  isAdded: boolean
}>()

defineEmits([
  'add'
])
</script>