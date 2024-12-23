<script setup lang="ts">
import ProfilePhoto from '../Logo/ProfilePhoto.vue'

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
      { href: '#', label: 'Add new', children: [], icon: null },
      { href: '#', label: '3-d level', children: [], icon: null },
    ],
    icon: null,
  },
]
</script>

<template>
  <div class="flex min-h-screen">
    <div class="w-64 shrink-0 text-white bg-gray-950 border-r border-gray-500 py-4">
      <div class="px-4">
        <a href="#" class="inline-block"><ProfilePhoto class="h-8 w-auto" /></a>
      </div>

      <nav>
        <template v-for="item in navItems" :key="item.label">
          <a class="flex" :href="item.href">{{ item.label }}</a>

          <div v-if="item.children.length">
            <a v-for="child in item.children" :key="child.label" :href="child.href">
              {{ child.label }}</a
            >
          </div>
        </template>

        <a href="#">Projects</a>

        <a href="">tasks</a>
        <div>
          <a href="#">all tasks</a>
          <a href="#">Add new</a>
          <div><a href="">3-d level</a></div>
        </div>
      </nav>
    </div>

    <main class="flex items-center justify-center">
      <p>Timer</p>
    </main>
  </div>
</template>
