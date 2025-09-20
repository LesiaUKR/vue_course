<template>
  <button :class="{ buttonClass }" @click="handleClick">
    {{ text }}
  </button>
</template>

<script setup>
import { computed } from 'vue'
const { text, type } = defineProps({
  text: {
    type: String,
    default: 'Sign in',
  },
  type: {
    type: String,
    default: 'primary',
  },
})

const buttonClass = computed(() => ({
  [type]: true,
}))

const handleClick = (event) => {
  console.log(event)
}
</script>
<style scoped>
button {
  @apply rounded px-5 py-3 font-medium;
}
.primary {
  @apply border-0 bg-brand-blue-1 text-white hover:shadow-blue;
}

.secondary {
}
</style>
