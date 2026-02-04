<template>
  <header class="flex justify-between items-center border-b border-primary px-10 py-8">
    <a href="#" class="flex items-center gap-4">
      <img src="/logo.png" class="w-10" alt="Logo" />
      <div>
        <h2 class="text-xl font-bold uppercase">Vue Sneakers</h2>
        <p class="text-muted">Магазин реактивных кроссовок</p>
      </div>
    </a>

    <nav>
      <ul class="flex items-center gap-10">
        <li class="nav-item flex items-center gap-3">
          <img src="/cart.svg" alt="Cart" class="icon-auto" />
          <span>1205 руб.</span>
        </li>
        <li class="nav-item flex items-center gap-3">
          <img src="/heart.svg" alt="Favorites" class="icon-auto" />
          <span>Избранное</span>
        </li>
        <li class="nav-item flex items-center gap-3">
          <img src="/profile.svg" alt="Profile" class="icon-auto" />
          <span>Профиль</span>
        </li>
        <li>
          <ThemeToggle />
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup lang="ts">
import ThemeToggle from './ThemeToggle.vue';
</script>
