<script setup>
import { ref } from 'vue'

const props = defineProps({
  task: {
    type: Object,
    required: true
  }
})

const emit = defineEmits(['toggle', 'delete', 'edit'])

const editing = ref(false)
const editedTitle = ref(props.task.title)

const startEdit = () => {
  editedTitle.value = props.task.title
  editing.value = true
}

const saveEdit = () => {
  const title = editedTitle.value.trim()

  if (!title) return

  emit('edit', {
    id: props.task.id,
    title
  })

  editing.value = false
}

const cancelEdit = () => {
  editing.value = false
  editedTitle.value = props.task.title
}
</script>

<template>
  <article class="task-item" :class="{ done: task.completed }">
    <button
      class="check"
      type="button"
      :aria-label="task.completed ? 'Marquer non terminée' : 'Marquer terminée'"
      @click="emit('toggle', task.id)"
    >
      {{ task.completed ? '✓' : '' }}
    </button>

    <div class="task-content">
      <template v-if="!editing">
        <span class="task-title">{{ task.title }}</span>
      </template>

      <template v-else>
        <input
          v-model="editedTitle"
          class="edit-input"
          @keyup.enter="saveEdit"
          @keyup.esc="cancelEdit"
        />
      </template>
    </div>

    <div class="actions">
      <template v-if="editing">
        <button class="action save" type="button" @click="saveEdit">
          Enregistrer
        </button>
        <button class="action" type="button" @click="cancelEdit">
          Annuler
        </button>
      </template>

      <template v-else>
        <button class="action" type="button" @click="startEdit">
          Modifier
        </button>
        <button
          class="action danger"
          type="button"
          @click="emit('delete', task.id)"
        >
          Supprimer
        </button>
      </template>
    </div>
  </article>
</template>