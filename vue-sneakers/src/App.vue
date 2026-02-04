<template>
  <!-- <Drawer /> -->
  <div class="bg-white dark:bg-gray-900 w-4/5 m-auto rounded-3xl shadow-xl mt-14 transition-colors">
    <Header />

    
    <div class="p-10">
      <h2 class="text-3xl font-bold mb-8">Все кроссовки</h2>

      <CardList />
    </div>
  </div>
</template>

<script setup lang="ts">
import Header from './components/Header.vue'
import CardList from './components/CardList.vue'
import Drawer from './components/Drawer.vue'
</script>

<style scoped></style>
