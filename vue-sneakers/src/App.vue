<template>
  <!-- <Drawer /> -->
  <div class="bg-white dark:bg-gray-900 w-4/5 m-auto rounded-3xl shadow-xl mt-14 transition-colors">
    <Header />

    <div class="p-10">
      <h2 class="text-3xl font-bold mb-4">Все кроссовки</h2>

      <div class="flex gap-5 justify-end items-center mb-10">
        <div class="relative">
          <img src="/search.svg" alt="Search" class="absolute left-4 top-3 dark:invert dark:opacity-75">
          <input 
            type="text" 
            class="border border-gray-300 dark:border-gray-700 rounded-2xl py-2 pl-11 pr-4 outline-none focus:border-gray-500 dark:focus:border-gray-500 transition-colors bg-white dark:bg-gray-800 text-gray-900 dark:text-gray-100"
            placeholder="Поиск..."
          />
        </div>
        <div class="relative custom-select">
          <button 
            class="border border-gray-300 dark:border-gray-700 rounded-2xl py-2 px-4 pr-10 outline-none focus:border-gray-500 dark:focus:border-gray-500 bg-white dark:bg-gray-800 cursor-pointer min-w-[200px] text-left text-gray-900 dark:text-gray-100 transition-colors"
            @click="toggleSelect"
          >
            {{ selectedLabel }}
          </button>
          <svg 
            class="absolute right-4 top-1/2 -translate-y-1/2 pointer-events-none dark:invert dark:opacity-75"
            width="12" 
            height="8" 
            viewBox="0 0 12 8" 
            fill="none" 
            xmlns="http://www.w3.org/2000/svg"
          >
            <path d="M1 1L6 6L11 1" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
          
          <div 
            v-show="isOpen"
            class="absolute top-full mt-2 w-full bg-white dark:bg-gray-800 border border-gray-300 z-20 dark:border-gray-700 rounded-2xl shadow-lg overflow-hidden"
          >
            <div 
              class="py-2 px-4 cursor-pointer hover:bg-gray-100 dark:hover:bg-gray-700 text-gray-900 dark:text-gray-100 transition-colors"
              @click="selectOption('name')" 
            >
              По названию
            </div>
            <div 
              class="py-2 px-4 cursor-pointer hover:bg-gray-100 dark:hover:bg-gray-700 text-gray-900 dark:text-gray-100 transition-colors"
              @click="selectOption('price')" 
            >
              Цена (по возрастанию)
            </div>
            <div 
              class="py-2 px-4 cursor-pointer hover:bg-gray-100 dark:hover:bg-gray-700 text-gray-900 dark:text-gray-100 transition-colors"
              @click="selectOption('-price')" 
            >
              Цена (по убыванию)
            </div>
          </div>
        </div>
      </div>

      <CardList :items="items"/>
    </div>
  </div>
</template>

<script setup lang="ts">
import { onMounted, ref, watch, computed } from 'vue';
import axios from 'axios';
import Header from './components/Header.vue'
import CardList from './components/CardList.vue'
// import Drawer from './components/Drawer.vue'

const items = ref([])
const sortBy = ref('')
// const searchQuerty = ref('')

const isOpen = ref(false)

const sortOptions = [
  { value: 'name', label: 'По названию' },
  { value: 'price', label: 'Цена (по возрастанию)' },
  { value: '-price', label: 'Цена (по убыванию)' }
]

const selectedLabel = computed(() => {
  const option = sortOptions.find(opt => opt.value === sortBy.value)
  return option ? option.label : 'Сортировать'
})

function toggleSelect() {
  isOpen.value = !isOpen.value
}

function selectOption(value: string) {
  sortBy.value = value
  isOpen.value = false
}

function handleClickOutside(event: MouseEvent) {
  const target = event.target as HTMLElement
  if (!target.closest('.custom-select')) {
    isOpen.value = false
  }
}

onMounted(async () => {
  try {
    const {data} = await axios.get('https://3e1138a16949c2f9.mokky.dev/items')
    items.value = data
  } catch (e) {
    console.warn(e)
  }

  document.addEventListener('click', handleClickOutside)
})

watch(sortBy, async() => {
  try {
    const {data} = await axios.get('https://3e1138a16949c2f9.mokky.dev/items?sortBy=' + sortBy.value)
    items.value = data
  } catch (e) {
    console.warn(e)
  }
})
</script>

<style scoped></style>