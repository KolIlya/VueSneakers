<template>
  <div class="flex items-center justify-between gap-4 border border-primary p-4 rounded-xl transition-colors">
    <div class="flex shrink-0">
      <img :src="imageUrl" alt="Sneaker" class="w-22 h-22 object-contain drop-shadow-md" />
    </div>

    <div class="flex flex-col">
      <span class="font-medium">{{ title }}</span>
      <span class="text-muted">{{ price }} руб.</span>
    </div>
    
    <CloseBtn />
  </div>
</template>

<script setup lang="ts">
import CloseBtn from './CloseBtn.vue';

defineProps<{
  imageUrl: string,
  title: string,
  price: number,
}>()

defineEmits([
])
</script>