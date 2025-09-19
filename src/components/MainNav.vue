<template>
  <header class="w-full text-sm">
    <div class="fixed left-0 top-0 h-16 w-full bg-white">
      <div
        class="mx-auto flex h-full flex-nowrap border-b border-solid border-brand-gray-1 px-8"
      >
        <a :href="companyUrl" class="flex h-full items-center text-xl">{{
          company
        }}</a>
        <nav class="ml-12 h-full">
          <ul class="flex h-full list-none">
            <li
              v-for="menuItem in menuItems"
              :key="menuItem"
              class="ml-9 h-full first:ml-0"
            >
              <a href="" class="flex h-full items-center py-2.5">{{
                menuItem
              }}</a>
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </header>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const company = ref('Bobo Careers')
const companyUrl = ref('https://bobocareers.com')
const menuItems = [
  'Teams',
  'Location',
  'Life at Bobo Corp',
  'How we hire',
  'Students',
  'Jobs',
]
</script>
