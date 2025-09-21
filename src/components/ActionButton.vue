<template>
  <button :class="buttonClass" @click="handleClick">
    {{ text }}
  </button>
</template>

<script setup>
import { computed } from 'vue'
const { text, type } = defineProps({
  text: {
    type: String,
    required: true,
    default: 'Sign in',
  },
  type: {
    type: String,
    required: false,
    default: 'primary',
    validator: (type) => ['primary', 'secondary'].includes(type),
  },
})

const buttonClass = computed(() => ({
  primary: type === 'primary',
  secondary: type === 'secondary',
}))

const handleClick = (event) => {
  console.log(event)
}
</script>
<style>
button {
  @apply rounded px-5 py-3 font-medium;
}
.primary {
  @apply border-0 bg-brand-blue-1 text-white hover:shadow-blue;
}

.secondary {
  @apply bg-transparent text-brand-blue-1 hover:bg-brand-blue-2 hover:text-white;
}
</style>
