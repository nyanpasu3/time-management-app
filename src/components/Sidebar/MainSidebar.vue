<script setup lang="ts">
import ProfilePhoto from '../Logo/ProfilePhoto.vue'
import NavItem from '../NavItem/NavItem.vue'

const navItems = [
  { href: '#', label: 'Profile', children: [], icon: null },
  {
    href: '#',
    label: 'Projects',
    children: [
      { href: '#', label: 'All projects', children: [], icon: null },
      { href: '#', label: 'Add new project', children: [], icon: null },
      { href: '#', label: 'something', children: [], icon: null },
    ],
    icon: null,
  },
  {
    href: '#',
    label: 'tasks',
    children: [
      { href: '#', label: 'all tasks', children: [], icon: null },
      {
        href: '#',
        label: 'Add new',
        children: [{ href: '#', label: '3-d level', children: [], icon: null }],
        icon: null,
      },
    ],
    icon: null,
  },
]
</script>

<template>
  <div class="flex min-h-screen">
    <div class="w-64 shrink-0 text-white bg-gray-950 border-r border-gray-950 py-4">
      <div class="px-4">
        <a href="#" class="inline-block"><ProfilePhoto class="h-8 w-auto" /></a>
      </div>

      <nav class="mt-2 px-2">
        <NavItem :item="item" v-for="item in navItems" :key="item.label" />
      </nav>
    </div>

    <main class="flex-grow flex items-center justify-center bg-gray-800 text-white flex-col">
      <p class="text-6xl mb-4">Task "something"</p>
      <p class="text-3xl text-white mb-6">30:00</p>
      <button
        class="px-6 py-2 bg-black text-white rounded-lg hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-300"
      >
        Старт
      </button>
    </main>
  </div>
</template>
