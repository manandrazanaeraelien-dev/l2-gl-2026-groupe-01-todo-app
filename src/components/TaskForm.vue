<script setup>
import { ref } from 'vue'

const title = ref('')
const priority = ref('medium')

const emit = defineEmits(['add-task'])

const submitTask = () => {
  const value = title.value.trim()

  if (!value) return

  emit('add-task', {
    title: value,
    priority: priority.value
  })

  title.value = ''
  priority.value = 'medium'
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

    <select
      v-model="priority"
      class="priority-select"
      aria-label="Priorité de la tâche"
    >
      <option value="high">🔴 Haute</option>
      <option value="medium">🟠 Moyenne</option>
      <option value="low">🟢 Basse</option>
    </select>

    <button type="submit">
      + Ajouter
    </button>

  </form>
</template>