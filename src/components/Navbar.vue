<template>
  <header class="relative flex items-center justify-between p-6 bg-white" >
    <RouterLink to="/" class="text-4xl font-serif italic z-[60]" @click="isOpen = false">P.</RouterLink>

    <nav class="hidden md:flex gap-8 text-lg">
      <RouterLink to="/about" class="hover:text-black">About</RouterLink>
      <RouterLink to="/projects" class="hover:text-black">Projects</RouterLink>
      <RouterLink to="/contact" class="hover:text-black">Contact</RouterLink>
    </nav>

    <button @click="isOpen = !isOpen" class="md:hidden z-50 p-2">
    <div class="w-6 h-6 relative">
        <span class="block absolute h-0.5 w-full bg-black transition-all duration-300 transform"
        :class="isOpen ? 'rotate-45 top-1/2 -translate-y-1/2' : 'top-0'"></span>
        <span class="block absolute h-0.5 w-full bg-black transition-all duration-300 top-1/2 -translate-y-1/2"
        :class="{'opacity-0': isOpen}"></span>
        <span class="block absolute h-0.5 w-full bg-black transition-all duration-300 transform"
        :class="isOpen ? '-rotate-45 top-1/2 -translate-y-1/2' : 'bottom-0'"></span>
    </div>
    </button>

<div v-if="isOpen" class="md:hidden fixed inset-0 bg-white/10 z-40 pt-20 px-6 backdrop-blur-[1px]">
      <div class="space-y-6">
        <RouterLink to="/about" class="block text-2xl" @click="isOpen = false">About</RouterLink>
        <RouterLink to="/projects" class="block text-2xl" @click="isOpen = false">Projects</RouterLink>
        <RouterLink to="/contact" class="block text-2xl" @click="isOpen = false">Contact</RouterLink>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue';
const isOpen = ref(false);
</script>

