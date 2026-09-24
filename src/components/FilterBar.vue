<script setup>
defineProps({
  currentFilter: {
    type: String,
    required: true
  }
})

const emit = defineEmits(['change-filter'])

const filters = [
  { value: 'all', label: 'Toutes' },
  { value: 'active', label: 'À faire' },
  { value: 'completed', label: 'Terminées' }
]
</script>

<template>
  <div class="filters">
    <button
      v-for="item in filters"
      :key="item.value"
      type="button"
      :class="{ active: currentFilter === item.value }"
      @click="emit('change-filter', item.value)"
    >
      {{ item.label }}
    </button>
  </div>
</template>