<script setup>
import TaskItem from './TaskItem.vue'

defineProps({
  tasks: {
    type: Array,
    required: true
  }
})

const emit = defineEmits(['toggle-task', 'delete-task', 'edit-task'])
</script>

<template>
  <div class="task-list">
    <div v-if="tasks.length === 0" class="empty">
      <div class="empty-icon">✓</div>
      <h2>Aucune tâche</h2>
      <p>Ajoutez une tâche ou changez le filtre.</p>
    </div>

    <TaskItem
      v-for="task in tasks"
      v-else
      :key="task.id"
      :task="task"
      @toggle="emit('toggle-task', $event)"
      @delete="emit('delete-task', $event)"
      @edit="emit('edit-task', $event)"
    />
  </div>
</template>