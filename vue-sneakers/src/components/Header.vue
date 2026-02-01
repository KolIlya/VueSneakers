<template>
  <header class="flex justify-between items-center border-b border-slate-300 px-10 py-8">
    <a href="#" class="flex items-center gap-4">
      <img src="/logo.png" class="w-10" alt="Logo" />
      <div>
        <h2 class="text-xl font-bold uppercase">Vue Sneakers</h2>
        <p class="text-slate-400">Магазин реактивных кроссовок</p>
      </div>
    </a>

    <nav>
      <ul class="flex items-center gap-10">
        <li class="flex items-center gap-3 text-gray-500 cursor-pointer hover:text-black">
          <img src="/cart.svg" alt="Cart" />
          <span>1205 руб.</span>
        </li>
        <li class="flex items-center gap-3 text-gray-500 cursor-pointer hover:text-black">
          <img src="/heart.svg" alt="Cart" />
          <span>Закладки</span>
        </li>
        <li class="flex items-center gap-3 text-gray-500 cursor-pointer hover:text-black">
          <img src="/profile.svg" alt="Profile" />
          <span>Профиль</span>
        </li>
      </ul>
    </nav>
  </header>
</template>
