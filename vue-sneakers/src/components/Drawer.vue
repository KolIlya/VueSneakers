<template>
    <div class="fixed top-0 left-0 h-full w-full bg-black dark:bg-black z-10 opacity-60"></div>
    <div class="drawer w-96 h-full fixed top-0 right-0 z-20 p-8 flex flex-col">
        <div class="flex items-center gap-5 mb-5">
            <button class="opacity-30 cursor-pointer rotate-180 transition hover:opacity-100 hover:-translate-x-1">
                <svg width="16" height="14" viewBox="0 0 16 14" fill="none" xmlns="http://www.w3.org/2000/svg" class="dark:invert">
                    <path d="M1 7H14.7143" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                    <path d="M8.71436 1L14.7144 7L8.71436 13" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
            </button>
            <h2 class="text-2xl font-bold">Корзина</h2>
        </div>

        <CartItemList />

        <div class="flex flex-col gap-4 mt-auto">
            <div class="flex items-center justify-between border-b border-slate-400 pb-2">
                <span>Итого:</span>
                <span>1200 ₽</span>
            </div>

            <button 
                class="bg-lime-500 transition-colors text-white py-3 rounded-3xl cursor-pointer hover:bg-lime-600 active:bg-lime-700 disabled:bg-slate-400"
            >
                Купить
            </button>
        </div>
    </div>
</template>

<script setup lang="ts">
import CartItemList from './CartItemList.vue';

defineProps<{
    total: number,
}>()

</script>