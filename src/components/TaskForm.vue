<script setup>
import { ref } from 'vue'

const title = ref('')

const emit = defineEmits(['add-task'])

const submitTask = () => {
  const value = title.value.trim()

  if (!value) return

  emit('add-task', value)
  title.value = ''
}
</script>

<template>
  <form class="task-form" @submit.prevent="submitTask">
    <input
      v-model="title"
      type="text"
      placeholder="Ex. Faire les exercices de JavaScript..."
      aria-label="Nom de la tâche"
    />
    <button type="submit">+ Ajouter</button>
  </form>
</template>