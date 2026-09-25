<script setup>
import { ref, computed, watch } from 'vue'
import TaskForm from './components/TaskForm.vue'
import FilterBar from './components/FilterBar.vue'

/* =========================
   MODE CLAIR / SOMBRE
========================= */

const isDarkMode = ref(
  localStorage.getItem('darkMode') === 'true'
)

function toggleDarkMode() {
  isDarkMode.value = !isDarkMode.value
  localStorage.setItem('darkMode', isDarkMode.value)
}

/* =========================
   TACHES
========================= */

const savedTasks = localStorage.getItem('tasks')

const tasks = ref(
  savedTasks
    ? JSON.parse(savedTasks).map(task => ({
        ...task,
        priority: task.priority || 'medium',
        completed: Boolean(task.completed)
      }))
    : [
        {
          id: 1,
          title: 'Préparer la présentation du projet',
          priority: 'high',
          completed: false
        },
        {
          id: 2,
          title: 'Faire les exercices de JavaScript',
          priority: 'medium',
          completed: false
        },
        {
          id: 3,
          title: 'Faire la présentation du projet',
          priority: 'low',
          completed: true
        }
      ]
)

/* =========================
   FILTRE / RECHERCHE
========================= */

const currentFilter = ref('all')
const searchQuery = ref('')

/* =========================
   NOTIFICATION
========================= */

const notification = ref('')
let notificationTimer = null

function showNotification(message) {
  notification.value = message

  clearTimeout(notificationTimer)

  notificationTimer = setTimeout(() => {
    notification.value = ''
  }, 2500)
}

/* =========================
   AJOUTER UNE TACHE
========================= */

function addTask(taskData) {
  const title =
    typeof taskData === 'string'
      ? taskData
      : taskData?.title

  const priority =
    typeof taskData === 'object'
      ? taskData.priority
      : 'medium'

  if (!title || !title.trim()) return

  tasks.value.push({
    id: Date.now(),
    title: title.trim(),
    priority: priority || 'medium',
    completed: false
  })

  showNotification('✅ Tâche ajoutée avec succès !')
}

/* =========================
   MODIFICATION
========================= */

const editingId = ref(null)
const editingTitle = ref('')
const editingPriority = ref('medium')

function editTask(task) {
  editingId.value = task.id
  editingTitle.value = task.title
  editingPriority.value = task.priority || 'medium'
}

function saveEdit(task) {
  if (!editingTitle.value.trim()) return

  task.title = editingTitle.value.trim()
  task.priority = editingPriority.value

  cancelEdit()

  showNotification('✏️ Tâche modifiée avec succès !')
}

function cancelEdit() {
  editingId.value = null
  editingTitle.value = ''
  editingPriority.value = 'medium'
}

/* =========================
   SUPPRESSION
========================= */

function deleteTask(id) {
  const confirmation = confirm(
    'Voulez-vous vraiment supprimer cette tâche ?'
  )

  if (!confirmation) return

  tasks.value = tasks.value.filter(
    task => task.id !== id
  )

  showNotification('🗑️ Tâche supprimée avec succès !')
}

/* =========================
   TERMINER UNE TACHE
========================= */

function toggleTask(task) {
  task.completed = !task.completed
}

/* =========================
   TOUT TERMINER
========================= */

function completeAllTasks() {
  if (tasks.value.length === 0) {
    showNotification('ℹ️ Aucune tâche disponible !')
    return
  }

  const hasUncompletedTasks = tasks.value.some(
    task => !task.completed
  )

  if (!hasUncompletedTasks) {
    showNotification(
      'ℹ️ Toutes les tâches sont déjà terminées !'
    )
    return
  }

  tasks.value.forEach(task => {
    task.completed = true
  })

  currentFilter.value = 'all'

  showNotification(
    '✅ Toutes les tâches sont terminées !'
  )
}

/* =========================
   TOUT REMETTRE A FAIRE
========================= */

function uncompleteAllTasks() {
  if (tasks.value.length === 0) {
    showNotification('ℹ️ Aucune tâche disponible !')
    return
  }

  const hasCompletedTasks = tasks.value.some(
    task => task.completed
  )

  if (!hasCompletedTasks) {
    showNotification(
      'ℹ️ Toutes les tâches sont déjà à faire !'
    )
    return
  }

  tasks.value.forEach(task => {
    task.completed = false
  })

  currentFilter.value = 'all'

  showNotification(
    '↩️ Toutes les tâches sont redevenues à faire !'
  )
}

/* =========================
   TACHES SUPPRIMEES
========================= */

const deletedTasks = ref(
  JSON.parse(
    localStorage.getItem('deletedTasks') || '[]'
  )
)

function deleteCompletedTasks() {
  const completedTasks = tasks.value.filter(
    task => task.completed
  )

  if (completedTasks.length === 0) {
    showNotification(
      'ℹ️ Aucune tâche terminée à supprimer !'
    )
    return
  }

  const confirmation = confirm(
    'Voulez-vous supprimer toutes les tâches terminées ?'
  )

  if (!confirmation) return

  deletedTasks.value = [...completedTasks]

  tasks.value = tasks.value.filter(
    task => !task.completed
  )

  currentFilter.value = 'all'

  showNotification(
    '🗑️ Tâches terminées supprimées !'
  )
}

/* =========================
   ANNULER SUPPRESSION
========================= */

function undoDeleteCompleted() {
  if (deletedTasks.value.length === 0) {
    showNotification(
      'ℹ️ Aucune suppression à annuler !'
    )
    return
  }

  const existingIds = new Set(
    tasks.value.map(task => task.id)
  )

  const tasksToRestore =
    deletedTasks.value.filter(
      task => !existingIds.has(task.id)
    )

  tasks.value = [
    ...tasks.value,
    ...tasksToRestore
  ]

  deletedTasks.value = []

  currentFilter.value = 'all'

  showNotification(
    '↩️ Suppression annulée ! Les tâches ont été restaurées.'
  )
}

/* =========================
   FILTRE
========================= */

function changeFilter(filter) {
  currentFilter.value = filter
}

const filteredTasks = computed(() => {
  let result = tasks.value

  if (searchQuery.value.trim()) {
    const search = searchQuery.value.toLowerCase().trim()

    result = result.filter(task =>
      task.title.toLowerCase().includes(search)
    )
  }

  if (currentFilter.value === 'todo') {
    result = result.filter(task => !task.completed)
  }

  if (currentFilter.value === 'done') {
    result = result.filter(task => task.completed)
  }

  return result
})
/* =========================
   STATISTIQUES
========================= */

const totalCount = computed(
  () => tasks.value.length
)

const completedCount = computed(
  () =>
    tasks.value.filter(
      task => task.completed
    ).length
)

const remainingCount = computed(
  () =>
    tasks.value.filter(
      task => !task.completed
    ).length
)

const progressPercentage = computed(() => {
  if (totalCount.value === 0) return 0

  return Math.round(
    (completedCount.value /
      totalCount.value) *
      100
  )
})

/* =========================
   PRIORITE
========================= */

function getPriorityLabel(priority) {
  if (priority === 'high') {
    return '🔴 Haute'
  }

  if (priority === 'low') {
    return '🟢 Basse'
  }

  return '🟠 Moyenne'
}

/* =========================
   LOCAL STORAGE
========================= */

watch(
  tasks,
  newTasks => {
    localStorage.setItem(
      'tasks',
      JSON.stringify(newTasks)
    )
  },
  { deep: true }
)

watch(
  deletedTasks,
  newDeletedTasks => {
    localStorage.setItem(
      'deletedTasks',
      JSON.stringify(newDeletedTasks)
    )
  },
  { deep: true }
)
</script>


<template>

  <div
    class="app"
    :class="{ 'dark-mode': isDarkMode }"
  >

    <!-- =========================
         HEADER
    ========================== -->

    <header class="header">

      <div>

        <p class="subtitle">
          MINI-PROJET • VUE 3 + VITE
        </p>

        <h1>
          Gestionnaire de tâches
        </h1>

        <p class="description">
          Organisez vos tâches quotidiennes simplement.
        </p>

      </div>


      <div class="header-actions">

        <button
          class="theme-button"
          @click="toggleDarkMode"
        >
          {{
            isDarkMode
              ? '☀️ Mode clair'
              : '🌙 Mode sombre'
          }}
        </button>


        <div class="remaining-card">

          <strong>
            {{ remainingCount }}
          </strong>

          <span>
            à faire
          </span>

        </div>

      </div>

    </header>


    <!-- =========================
         STATISTIQUES
    ========================== -->

    <section class="stats">

      <div class="stat-card">

        <span class="stat-icon">
          📋
        </span>

        <div>

          <strong>
            {{ totalCount }}
          </strong>

          <span>
            Total
          </span>

        </div>

      </div>


      <div class="stat-card">

        <span class="stat-icon">
          ⏳
        </span>

        <div>

          <strong>
            {{ remainingCount }}
          </strong>

          <span>
            À faire
          </span>

        </div>

      </div>


      <div class="stat-card">

        <span class="stat-icon">
          ✅
        </span>

        <div>

          <strong>
            {{ completedCount }}
          </strong>

          <span>
            Terminées
          </span>

        </div>

      </div>


      <div class="stat-card">

        <span class="stat-icon">
          📈
        </span>

        <div>

          <strong>
            {{ progressPercentage }}%
          </strong>

          <span>
            Progression
          </span>

        </div>

      </div>

    </section>


    <!-- =========================
         PROGRESSION
    ========================== -->

    <section class="progress-section">

      <div class="progress-header">

        <span>
          Progression
        </span>

        <strong>
          {{ progressPercentage }}%
        </strong>

      </div>


      <div class="progress-bar">

        <div
          class="progress-fill"
          :style="{
            width: progressPercentage + '%'
          }"
        ></div>

      </div>

    </section>


    <!-- =========================
         AJOUT TACHE
    ========================== -->

    <section class="card">

      <h2>
        ➕ Ajouter une tâche
      </h2>

      <TaskForm
        @add-task="addTask"
      />

    </section>


    <!-- =========================
         RECHERCHE
    ========================== -->

    <section class="search-section">

      <input
        v-model="searchQuery"
        type="text"
        placeholder="🔎 Rechercher une tâche..."
      />

    </section>


    <!-- =========================
         FILTRES
    ========================== -->

    <section class="filter-section">
  <FilterBar
    :current-filter="currentFilter"
    @change-filter="changeFilter"
  />
</section>


    <!-- =========================
         ACTIONS
    ========================== -->

    <section class="bulk-actions">

      <button
        class="action-button success"
        @click="completeAllTasks"
      >
        ✅ Tout terminer
      </button>


      <button
        class="action-button"
        @click="uncompleteAllTasks"
      >
        ↩️ Tout remettre à faire
      </button>


      <button
        class="action-button danger"
        @click="deleteCompletedTasks"
      >
        🗑️ Supprimer terminées
      </button>


      <button
        class="action-button warning"
        @click="undoDeleteCompleted"
      >
        ↩️ Annuler suppression
      </button>

    </section>


    <!-- =========================
         NOTIFICATION
    ========================== -->

    <div
      v-if="notification"
      class="notification"
    >
      {{ notification }}
    </div>


    <!-- =========================
         LISTE DES TACHES
    ========================== -->

    <section class="tasks-section">

      <!-- AUCUNE TACHE -->

      <div
        v-if="filteredTasks.length === 0"
        class="empty-state"
      >

        <div class="empty-icon">
          📭
        </div>

        <h3>
          Aucune tâche trouvée
        </h3>

        <p>
          Ajoutez une nouvelle tâche pour commencer.
        </p>

      </div>


      <!-- LISTE -->

      <div
        v-for="task in filteredTasks"
        :key="task.id"
        class="task-card"
        :class="{ completed: task.completed }"
      >

        <!-- =========================
             MODE EDITION
        ========================== -->

        <div
          v-if="editingId === task.id"
          class="edit-form"
        >

          <input
            v-model="editingTitle"
            type="text"
            @keyup.enter="saveEdit(task)"
          />


          <select
            v-model="editingPriority"
          >

            <option value="high">
              🔴 Haute
            </option>

            <option value="medium">
              🟠 Moyenne
            </option>

            <option value="low">
              🟢 Basse
            </option>

          </select>


          <div class="edit-actions">

            <button
              class="save-button"
              @click="saveEdit(task)"
            >
              💾 Enregistrer
            </button>


            <button
              class="cancel-button"
              @click="cancelEdit"
            >
              Annuler
            </button>

          </div>

        </div>


        <!-- =========================
             MODE NORMAL
        ========================== -->

        <template v-else>

          <div class="task-main">

            <button
              class="check-button"
              :class="{
                checked: task.completed
              }"
              @click="toggleTask(task)"
            >
              {{
                task.completed
                  ? '✓'
                  : ''
              }}
            </button>


            <div class="task-info">

              <h3>
                {{ task.title }}
              </h3>


              <span
                class="priority"
                :class="
                  'priority-' +
                  task.priority
                "
              >
                {{ getPriorityLabel(task.priority) }}
              </span>

            </div>

          </div>


          <div class="task-actions">

            <button
              class="edit-button"
              @click="editTask(task)"
            >
              ✏️ Modifier
            </button>


            <button
              class="delete-button"
              @click="
                deleteTask(task.id)
              "
            >
              🗑️ Supprimer
            </button>

          </div>

        </template>

      </div>

    </section>


    <!-- =========================
         FOOTER
    ========================== -->

    <footer>

      <p>
        Mini-projet Vue.js 3 + Vite
      </p>

      <p>
        Gestionnaire de tâches — Groupe 01
      </p>

    </footer>

  </div>

</template>