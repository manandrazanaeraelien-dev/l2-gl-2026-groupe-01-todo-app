<script setup>
import { computed, ref, watch } from 'vue'
import TaskForm from './components/TaskForm.vue'
import TaskList from './components/TaskList.vue'
import FilterBar from './components/FilterBar.vue'

const savedTasks = localStorage.getItem('todo-tasks')

const tasks = ref(
  savedTasks
    ? JSON.parse(savedTasks)
    : [
        {
          id: 1,
          title: 'Préparer le mini-projet Vue.js',
          completed: false
        },
        {
          id: 2,
          title: 'Créer les composants',
          completed: true
        }
      ]
)

const filter = ref('all')

const addTask = (title) => {
  tasks.value.unshift({
    id: Date.now(),
    title,
    completed: false
  })
}

const toggleTask = (id) => {
  const task = tasks.value.find(task => task.id === id)
  if (task) task.completed = !task.completed
}

const deleteTask = (id) => {
  tasks.value = tasks.value.filter(task => task.id !== id)
}

const editTask = ({ id, title }) => {
  const task = tasks.value.find(task => task.id === id)
  if (task) task.title = title
}

const filteredTasks = computed(() => {
  if (filter.value === 'active') {
    return tasks.value.filter(task => !task.completed)
  }
  if (filter.value === 'completed') {
    return tasks.value.filter(task => task.completed)
  }
  return tasks.value
})

const remainingCount = computed(() =>
  tasks.value.filter(task => !task.completed).length
)

watch(
  tasks,
  value => {
    localStorage.setItem('todo-tasks', JSON.stringify(value))
  },
  { deep: true }
)
</script>

<template>
  <main class="app">
    <section class="card">
      <header class="header">
        <div>
          <p class="eyebrow">MINI-PROJET • VUE 3 + VITE</p>
          <h1>Gestionnaire de tâches</h1>
          <p class="subtitle">
            Organisez vos tâches quotidiennes simplement.
          </p>
        </div>
        <div class="counter">
          <strong>{{ remainingCount }}</strong>
          <span>à faire</span>
        </div>
      </header>

      <TaskForm @add-task="addTask" />

      <FilterBar
        :current-filter="filter"
        @change-filter="filter = $event"
      />

      <TaskList
        :tasks="filteredTasks"
        @toggle-task="toggleTask"
        @delete-task="deleteTask"
        @edit-task="editTask"
      />

      <footer class="footer">
        <span>{{ tasks.length }} tâche(s) au total</span>
        <span>•</span>
        <span>Données sauvegardées automatiquement</span>
      </footer>
    </section>
  </main>
</template>