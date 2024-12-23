<script setup lang="ts">
import logo from '@/assets/img/logo.png'
</script>

<template>
  <RouterLink class="flex flex-shrink-0 items-center mr-4" to="/">
    <img class="h-10 w-auto" :src="logo" alt="Vue Jobs" />
    <span class="hidden md:block text-white text-2xl font-bold ml-2">Nyan Pasu</span>
  </RouterLink>
</template>
