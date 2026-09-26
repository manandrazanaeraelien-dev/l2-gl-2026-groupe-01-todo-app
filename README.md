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
├── Capture-1.png
├── Capture-2.png
├── Capture-3.png
├── Capture-4.png
├── Capture-5.png
├── Capture-6.png
├── Capture-7.png
├── Capture-8.png
├── Capture-9.png
├── Capture-10.png
├── Capture-11.png
├── Capture-12.png
├── Capture-13.png
│
├── package.json
├── vite.config.js
└── README.md
```

---

# 8. 📸 Captures d'écran

Cette section présente les différentes interfaces et fonctionnalités de l'application.

## 🖥️ Capture 1 — Interface principale

<p align="center">
  <img src="./Capture-1.png" width="80%" alt="Capture 1 - Interface principale">
</p>

---

## 🌙 Capture 2 — Interface en mode sombre

<p align="center">
  <img src="./Capture-2.png" width="80%" alt="Capture 2 - Mode sombre">
</p>

---

## ➕ Capture 3 — Ajout d'une tâche

<p align="center">
  <img src="./Capture-3.png" width="80%" alt="Capture 3 - Ajout d'une tâche">
</p>

---

## 🗑️ Capture 4 — Confirmation de suppression

<p align="center">
  <img src="./Capture-4.png" width="80%" alt="Capture 4 - Confirmation de suppression">
</p>

---

## 📋 Capture 5 — Gestion des tâches

<p align="center">
  <img src="./Capture-5.png" width="80%" alt="Capture 5 - Gestion des tâches">
</p>

---

## ✏️ Capture 6 — Modification et gestion des tâches

<p align="center">
  <img src="./Capture-6.png" width="80%" alt="Capture 6 - Modification des tâches">
</p>

---

## 🔎 Capture 7 — Recherche et filtrage des tâches

<p align="center">
  <img src="./Capture-7.png" width="80%" alt="Capture 7 - Recherche et filtrage">
</p>

---

## 🔽 Capture 8 — Filtre des tâches terminées

<p align="center">
  <img src="./Capture-8.png" width="80%" alt="Capture 8 - Filtre des tâches terminées">
</p>

---

## ⏳ Capture 9 — Filtrage des tâches à faire

<p align="center">
  <img src="./Capture-9.png" width="80%" alt="Capture 9 - Filtrage des tâches à faire">
</p>

---

## ✅ Capture 10 — Affichage des tâches terminées

<p align="center">
  <img src="./Capture-10.png" width="80%" alt="Capture 10 - Tâches terminées">
</p>

---

## 📊 Capture 11 — Statistiques et progression

<p align="center">
  <img src="./Capture-11.png" width="80%" alt="Capture 11 - Statistiques et progression">
</p>

---

## 🔄 Capture 12 — Retour à l'état initial des tâches

<p align="center">
  <img src="./Capture-12.png" width="80%" alt="Capture 12 - Retour à l'état initial">
</p>

---

## 📝 Capture 13 — Interface de gestion des tâches

<p align="center">
  <img src="./Capture-13.png" width="80%" alt="Capture 13 - Gestion des tâches">
</p>

---

## 9. 💾 Stockage des données avec LocalStorage

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

Le mode sombre et les tâches supprimées peuvent également être conservés dans `localStorage`.

---

## 10. 🎨 Interface utilisateur

L'interface a été conçue pour être simple, claire et facile à utiliser.

Elle contient notamment :

- Un en-tête présentant le projet
- Un bouton de changement de thème
- Des statistiques
- Une barre de progression
- Un formulaire d'ajout
- Une barre de recherche
- Des filtres
- Des boutons d'actions
- Une liste des tâches
- Des notifications d'information

---

## 11. ⭐ Gestion des priorités

Chaque tâche possède une priorité.

Les trois niveaux disponibles sont :

- 🔴 **Haute**
- 🟠 **Moyenne**
- 🟢 **Basse**

La priorité peut être choisie lors de l'ajout d'une tâche et peut également être modifiée.

---

## 12. 🌙 Mode sombre et mode clair

L'application possède deux modes d'affichage :

- ☀️ **Mode clair**
- 🌙 **Mode sombre**

Le choix du thème est sauvegardé dans `localStorage`.

Ainsi, le thème sélectionné peut être conservé après actualisation de la page.

---

## 13. 📊 Statistiques et progression

L'application affiche automatiquement plusieurs statistiques :

- 📋 Nombre total de tâches
- ⏳ Nombre de tâches à faire
- ✅ Nombre de tâches terminées
- 📈 Pourcentage de progression

Le pourcentage de progression est calculé automatiquement à partir du nombre de tâches terminées.

---

## 14. 🔎 Recherche et filtrage

La barre de recherche permet de rechercher rapidement une tâche à partir de son titre.

Les filtres permettent d'afficher :

- **Toutes** : toutes les tâches
- **À faire** : uniquement les tâches non terminées
- **Terminées** : uniquement les tâches terminées

La combinaison de la recherche et des filtres facilite l'organisation des tâches.

---

## 15. 🔄 Actions globales

L'application propose également plusieurs actions globales :

- **Tout terminer**
- **Tout remettre à faire**
- **Supprimer les tâches terminées**
- **Annuler une suppression**

Ces actions permettent de gérer rapidement plusieurs tâches.

---

## 16. 📱 Responsive Design

L'interface a été conçue pour s'adapter à différentes tailles d'écran.

Elle peut être utilisée sur :

- 💻 Ordinateur
- 📱 Téléphone
- 📟 Tablette

Le CSS permet d'adapter la disposition des éléments selon la largeur de l'écran.

---

## 17. 🚀 Installation du projet

### Cloner le projet

```bash
git clone https://github.com/votre-compte/vue3-todo-mini-project.git
```

### Entrer dans le dossier

```bash
cd vue3-todo-mini-project
```

### Installer les dépendances

```bash
npm install
```

### Lancer le serveur de développement

```bash
npm run dev
```

Vite indique ensuite l'adresse locale permettant d'ouvrir l'application dans le navigateur.

---

## 18. 🔧 Commandes Git principales

Ajouter les modifications :

```bash
git add .
```

Créer un commit :

```bash
git commit -m "Finalisation du mini-projet Vue 3"
```

Envoyer les modifications vers GitHub :

```bash
git push
```

---

## 19. 🌐 Déploiement

Le projet peut être déployé avec **GitHub Pages** afin de rendre l'application accessible en ligne.

Le déploiement utilise une configuration adaptée à **Vite** et peut être automatisé avec **GitHub Actions**.

---

## 20. 🎓 Conclusion

Ce mini-projet nous a permis de mettre en pratique les principales notions de **Vue.js 3** et de mieux comprendre le fonctionnement d'une application web moderne.

Nous avons notamment appris à :

- Créer des composants Vue.js
- Manipuler des données réactives
- Utiliser les directives Vue.js
- Gérer les événements
- Utiliser `props` et `emit`
- Utiliser `ref()`, `computed()` et `watch()`
- Sauvegarder des données avec `localStorage`
- Créer une interface responsive
- Organiser un projet avec Vue.js et Vite
- Utiliser Git et GitHub
- Déployer une application web

Ce projet constitue ainsi une application complète de gestion de tâches réalisée avec **Vue.js 3 + Vite**.
