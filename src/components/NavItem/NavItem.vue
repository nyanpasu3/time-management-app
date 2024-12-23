<script setup lang="ts">
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue'

const props = defineProps({
  item: Object,
})
</script>

<template>
  <a
    v-if="!item.children.length"
    :class="[
      'group flex w-full items-center rounded-md py-2 px-3 text-sm font-medium text-gray-50 mr-2 hover:bg-gray-800',
    ]"
    :href="item.href"
    ><component
      :class="['h-6 w-6 shrink-0 text-blue-400 group-hover:text-blue-600']"
      :is="item.icon"
      v-if="item.icon"
    ></component>
    <span>{{ item.label }}</span>
  </a>

  <Disclosure v-else>
    <DisclosureButton
      :class="[
        'flex w-full text-left items-center rounded-md py-2 px-3 text-sm font-medium text-white mr-2 hover:bg-gray-800',
      ]"
    >
      <component :class="['w-6 h-6 shrink-0']" :is="item.icon" v-if="item.icon"></component>
      <span class="flex-1">{{ item.label }}</span>
    </DisclosureButton>
    <DisclosurePanel class="ml-4">
      <NavItem v-for="child in item.children" :item="child" />
    </DisclosurePanel>
  </Disclosure>
</template>
