# 📝 Mini-projet Vue 3 + Vite — Gestionnaire de tâches

## 1. Présentation

Application web réalisée avec **Vue.js 3** et **Vite** permettant de gérer des tâches quotidiennes.

Ce projet a été réalisé dans le cadre du mini-projet **Introduction aux Frameworks JavaScript** en Licence 2 — Génie Informatique / Génie Logiciel.

L'application permet à l'utilisateur d'ajouter, modifier, supprimer, rechercher et organiser ses tâches.

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

## 3. Fonctionnalités

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

## 5. Notions Vue.js utilisées

Le projet respecte les principales consignes du mini-projet.

### `v-model`

Utilisé pour assurer la liaison entre les champs du formulaire et les données JavaScript.

Exemple :

```html
<input v-model="newTask">
