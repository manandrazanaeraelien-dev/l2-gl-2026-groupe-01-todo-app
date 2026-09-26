# 📝 Mini-projet Vue 3 + Vite — Gestionnaire de tâches

## 1. Présentation du projet

Application web réalisée avec **Vue.js 3** et **Vite** permettant de gérer des tâches quotidiennes.

Ce projet a été réalisé dans le cadre du mini-projet **Introduction aux Frameworks JavaScript** en Licence 2 — Génie Informatique / Génie Logiciel.

L'application permet à l'utilisateur d'ajouter, modifier, supprimer, rechercher et organiser ses tâches facilement.

---

## 2. Objectif du projet

L'objectif de ce mini-projet est de mettre en pratique les principales notions de **Vue.js 3**, notamment :

- La création de composants
- La gestion des données réactives
- Les formulaires
- Les événements
- Les `props`
- Les `emit`
- Les directives Vue.js
- `ref()`
- `computed()`
- `watch()`
- `localStorage`
- L'organisation d'un projet Vue.js
- L'utilisation de Git et GitHub

---

## 3. Membres du groupe

1. **RAJAOSOLO Manandrazana Eraelien**
2. **RASOLOFOHARIFARA Marie Rosa**
3. **RAKOTOARIMALALA Mitia Mendrika Hankasitrahina**
4. **ANDRIAMAMPIHAJA Carmelo**

---

## 4. Technologies utilisées

- **Vue.js 3**
- **Vite**
- **JavaScript**
- **HTML5**
- **CSS3**
- **LocalStorage**
- **Git**
- **GitHub**

---

## 5. Fonctionnalités

L'application possède les fonctionnalités suivantes :

- ➕ Ajouter une tâche
- ✏️ Modifier une tâche
- 🗑️ Supprimer une tâche
- ✅ Marquer une tâche comme terminée
- 🔄 Marquer une tâche comme non terminée
- 🔎 Rechercher une tâche
- 🔽 Filtrer les tâches
- 📊 Afficher les statistiques
- 📈 Afficher le pourcentage de progression
- ⭐ Gérer les priorités
- 🌙 Mode sombre
- ☀️ Mode clair
- 💾 Sauvegarde automatique dans `localStorage`
- 🔄 Conservation des données après actualisation
- 📱 Interface adaptée à différents écrans

### Filtres disponibles

L'utilisateur peut afficher :

- Toutes les tâches
- Les tâches à faire
- Les tâches terminées

---

## 6. Notions Vue.js utilisées

### `v-model`

Utilisé pour assurer la liaison entre les champs du formulaire et les données JavaScript.

```html
<input v-model="newTask">
<div v-for="task in tasks" :key="task.id">
  {{ task.title }}
</div>
<p v-if="task.completed">
  Tâche terminée
</p>
<button @click="addTask">
  Ajouter
</button>
const tasks = ref([])
const completedTasks = computed(() => {
  return tasks.value.filter(task => task.completed)
})
vue3-todo-mini-project/
│
├── src/
│   ├── components/
│   │   ├── TaskForm.vue
│   │   ├── TaskList.vue
│   │   ├── TaskItem.vue
│   │   └── FilterBar.vue
│   │
│   ├── App.vue
│   └── main.js
│
├── public/
│
├── Affichage des tâches terminées.png
├── Ajout d’une tâche.png
├── Confirmation de suppression des tâches terminées.png
├── Filtrage des tâches à faire.png
├── Filtre des tâches terminées.png
├── Gestion des tâche.png
├── Gestion des tâches.png
├── Interface en mode sombre.png
├── Interface principale (1).png
├── Interface principale.png
├── Recherche et filtrage des tâche.png
├── Retour à l’état initial des tâches.png
├── Statistiques et progression des tâches.png
│
├── package.json
├── vite.config.js
└── README.md
# 📸 19. Captures d'écran

<p align="center">
  <img src="Interface%20principale.png" width="45%" alt="Interface principale" />
  <img src="Interface%20en%20mode%20sombre.png" width="45%" alt="Interface mode sombre" />
</p>

<p align="center">
  <img src="Ajout%20d’une%20tâche.png" width="45%" alt="Ajout d'une tâche" />
  <img src="Confirmation%20de%20suppression%20des%20tâches%20terminées.png" width="45%" alt="Confirmation suppression" />
</p>

<p align="center">
  <img src="Gestion%20des%20tâche.png" width="45%" alt="Gestion des tâches 1" />
  <img src="Gestion%20des%20tâches.png" width="45%" alt="Gestion des tâches 2" />
</p>

<p align="center">
  <img src="Recherche%20et%20filtrage%20des%20tâche.png" width="45%" alt="Recherche et filtrage" />
  <img src="Filtre%20des%20tâches%20terminées.png" width="45%" alt="Filtre tâches terminées" />
</p>

<p align="center">
  <img src="Filtrage%20des%20tâches%20à%20faire.png" width="45%" alt="Filtrage à faire" />
  <img src="Affichage%20des%20tâches%20terminées.png" width="45%" alt="Affichage terminées" />
</p>

<p align="center">
  <img src="Statistiques%20et%20progression%20des%20tâches.png" width="45%" alt="Statistiques" />
  <img src="Retour%20à%20l’état%20initial%20des%20tâches.png" width="45%" alt="Retour état initial" />
</p>

