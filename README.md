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

### 6.1 `v-model`

La directive `v-model` permet de créer une liaison entre les champs du formulaire et les données JavaScript.

```html
<input v-model="newTask">
```

Elle permet de récupérer automatiquement la valeur saisie par l'utilisateur.

---

### 6.2 `v-for`

La directive `v-for` permet d'afficher plusieurs éléments à partir d'une liste.

```html
<div v-for="task in tasks" :key="task.id">
  {{ task.title }}
</div>
```

Dans notre application, elle est utilisée pour afficher les différentes tâches.

---

### 6.3 `v-if` et `v-else`

Ces directives permettent d'afficher un élément selon une condition.

```html
<p v-if="task.completed">
  Tâche terminée
</p>

<p v-else>
  Tâche à faire
</p>
```

---

### 6.4 Les événements

Vue.js permet de gérer les actions de l'utilisateur avec des événements comme `@click`, `@submit` et `@keyup`.

Exemple :

```html
<button @click="addTask">
  Ajouter
</button>
```

---

### 6.5 `ref()`

`ref()` permet de créer une donnée réactive dans Vue.js.

```javascript
import { ref } from 'vue'

const tasks = ref([])
```

Lorsque la valeur de `tasks` change, l'interface est automatiquement mise à jour.

---

### 6.6 `computed()`

`computed()` permet de créer une valeur calculée automatiquement à partir des données réactives.

```javascript
const completedTasks = computed(() => {
  return tasks.value.filter(task => task.completed)
})
```

Dans notre projet, les propriétés calculées permettent notamment de déterminer :

- Le nombre total de tâches
- Le nombre de tâches terminées
- Le nombre de tâches restantes
- Le pourcentage de progression
- Les tâches filtrées

---

### 6.7 `watch()`

`watch()` permet de surveiller les changements d'une donnée.

Dans notre projet, il est utilisé notamment pour sauvegarder automatiquement les tâches dans `localStorage`.

```javascript
watch(
  tasks,
  (newTasks) => {
    localStorage.setItem('tasks', JSON.stringify(newTasks))
  },
  { deep: true }
)
```

---

### 6.8 `props`

Les `props` permettent de transmettre des données d'un composant parent vers un composant enfant.

Exemple :

```javascript
defineProps({
  currentFilter: {
    type: String,
    required: true
  }
})
```

---

### 6.9 `emit`

Les événements `emit` permettent à un composant enfant de communiquer avec son composant parent.

Exemple :

```javascript
const emit = defineEmits(['change-filter'])
```

---

## 7. Organisation du projet

```text
vue3-todo-mini-project/
│
├── public/
│   └── captures/
│       ├── interface-principale.png
│       ├── mode-sombre.png
│       ├── ajout-tache.png
│       ├── confirmation-suppression.png
│       ├── gestion-taches-1.png
│       ├── gestion-taches-2.png
│       ├── recherche-filtrage.png
│       ├── filtre-terminees.png
│       ├── filtre-a-faire.png
│       ├── affichage-terminees.png
│       ├── statistiques-progression.png
│       └── retour-etat-initial.png
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
├── package.json
├── vite.config.js
└── README.md
```

---

# 📸 8. Captures d'écran

Les captures suivantes présentent les principales fonctionnalités de l'application.

## 🖥️ Interface principale

<p align="center">
  <img src="public/captures/interface-principale.png" width="80%" alt="Interface principale">
</p>

---

## 🌙 Interface en mode sombre

<p align="center">
  <img src="public/captures/mode-sombre.png" width="80%" alt="Interface en mode sombre">
</p>

---

## ➕ Ajout d'une tâche

<p align="center">
  <img src="public/captures/ajout-tache.png" width="80%" alt="Ajout d'une tâche">
</p>

---

## 🗑️ Confirmation de suppression

<p align="center">
  <img src="public/captures/confirmation-suppression.png" width="80%" alt="Confirmation de suppression">
</p>

---

## 📋 Gestion des tâches

<p align="center">
  <img src="public/captures/gestion-taches-1.png" width="80%" alt="Gestion des tâches">
</p>

<p align="center">
  <img src="public/captures/gestion-taches-2.png" width="80%" alt="Gestion des tâches">
</p>

---

## 🔎 Recherche et filtrage des tâches

<p align="center">
  <img src="public/captures/recherche-filtrage.png" width="80%" alt="Recherche et filtrage des tâches">
</p>

---

## 🔽 Filtre des tâches terminées

<p align="center">
  <img src="public/captures/filtre-terminees.png" width="80%" alt="Filtre des tâches terminées">
</p>

---

## ⏳ Filtrage des tâches à faire

<p align="center">
  <img src="public/captures/filtre-a-faire.png" width="80%" alt="Filtrage des tâches à faire">
</p>

---

## ✅ Affichage des tâches terminées

<p align="center">
  <img src="public/captures/affichage-terminees.png" width="80%" alt="Affichage des tâches terminées">
</p>

---

## 📊 Statistiques et progression

<p align="center">
  <img src="public/captures/statistiques-progression.png" width="80%" alt="Statistiques et progression des tâches">
</p>

---

## 🔄 Retour à l'état initial des tâches

<p align="center">
  <img src="public/captures/retour-etat-initial.png" width="80%" alt="Retour à l'état initial des tâches">
</p>

---

## 9. Stockage des données

L'application utilise **localStorage** pour conserver les tâches dans le navigateur.

Ainsi, les données restent disponibles même après l'actualisation de la page.

Exemple :

```javascript
localStorage.setItem(
  'tasks',
  JSON.stringify(tasks.value)
)
```

Pour récupérer les données :

```javascript
const savedTasks = localStorage.getItem('tasks')
```

---

## 10. Interface utilisateur

L'interface a été conçue pour être simple et facile à utiliser.

Elle contient notamment :

- Un en-tête présentant le projet
- Un bouton de changement de thème
- Des statistiques
- Une barre de progression
- Un formulaire d'ajout
- Une recherche
- Des filtres
- Des boutons d'actions
- Une liste des tâches

---

## 11. Gestion des priorités

Chaque tâche possède une priorité :

- 🔴 **Haute**
- 🟠 **Moyenne**
- 🟢 **Basse**

La priorité peut être choisie lors de l'ajout ou modifiée ensuite.

---

## 12. Mode sombre et mode clair

L'application possède deux thèmes :

- ☀️ Mode clair
- 🌙 Mode sombre

Le choix du thème est sauvegardé dans `localStorage`.

Ainsi, le thème sélectionné peut être conservé après actualisation de la page.

---

## 13. Statistiques

L'application affiche automatiquement :

- 📋 Le nombre total de tâches
- ⏳ Le nombre de tâches à faire
- ✅ Le nombre de tâches terminées
- 📈 Le pourcentage de progression

Le pourcentage est calculé automatiquement à partir du nombre de tâches terminées.

---

## 14. Installation du projet

Cloner le projet :

```bash
git clone https://github.com/votre-compte/vue3-todo-mini-project.git
```

Entrer dans le projet :

```bash
cd vue3-todo-mini-project
```

Installer les dépendances :

```bash
npm install
```

Lancer le serveur de développement :

```bash
npm run dev
```

L'application est ensuite accessible dans le navigateur à l'adresse indiquée par Vite.

---

## 15. Git et GitHub

Le projet est versionné avec **Git** et peut être publié sur **GitHub**.

Commandes principales :

```bash
git add .
git commit -m "Finalisation du mini-projet Vue 3"
git push
```

---

## 16. Conclusion

Ce mini-projet nous a permis de mettre en pratique les principales notions de **Vue.js 3** et de mieux comprendre le fonctionnement d'une application web moderne.

Nous avons notamment appris à :

- Créer des composants Vue.js
- Manipuler des données réactives
- Utiliser les directives Vue.js
- Gérer les événements
- Utiliser `props` et `emit`
- Utiliser `ref`, `computed` et `watch`
- Sauvegarder des données avec `localStorage`
- Organiser un projet avec Vue.js et Vite
- Utiliser Git et GitHub

Le projet constitue ainsi une application complète de gestion de tâches réalisée avec **Vue.js 3 + Vite**.
