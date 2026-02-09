<template>
  <div class="grid grid-cols-4 gap-5 ">
    <Card
      v-for="item in items"
      :key="item.id"
      :title="item.title"
      :image-url="item.imageUrl"
      :price="item.price"
      :is-favorite="false"
      :is-added="false"
    />
  </div>
</template>

<script setup lang="ts">
import type { Sneaker } from '../types/index.ts'
import Card from './Card.vue'

defineProps<{
  items: Sneaker[],
}>()
</script>