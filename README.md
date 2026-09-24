# Mini-projet Vue 3 + Vite — Gestionnaire de tâches

## 1. Présentation

Application web réalisée avec **Vue.js 3** et **Vite** permettant de gérer des tâches quotidiennes.

## 2. Fonctionnalités

- Ajouter une tâche
- Modifier une tâche
- Supprimer une tâche
- Marquer une tâche comme terminée / non terminée
- Filtrer : toutes / à faire / terminées
- Compteur des tâches restantes
- Sauvegarde automatique dans `localStorage`
- Interface responsive pour ordinateur

## 3. Notions Vue.js utilisées

Le projet respecte les consignes du mini-projet :

- `v-model` : liaison du formulaire et des champs de modification
- `v-for` : affichage des tâches et des filtres
- `v-if` / `v-else` : affichage conditionnel
- événements : `@submit`, `@click`, `@keyup`
- `props` : transmission des tâches et du filtre aux composants
- `emit` : communication enfant → parent
- `ref()` : état réactif simple
- `computed()` : calcul des tâches filtrées et du compteur
- `watch()` : sauvegarde automatique dans `localStorage`

## 4. Organisation

```text
vue3-todo-mini-projet/
├── index.html
├── package.json
├── vite.config.js
├── README.md
└── src/
    ├── main.js
    ├── App.vue
    ├── style.css
    └── components/
        ├── TaskForm.vue
        ├── TaskList.vue
        ├── TaskItem.vue
        └── FilterBar.vue
```

## 5. Installation

Installer Node.js, puis ouvrir un terminal dans le dossier du projet :

```bash
npm install
npm run dev
```

Vite affichera une adresse locale, généralement :

```text
http://localhost:5173
```

Pour tester la version de production :

```bash
npm run build
npm run preview
```

## 6. Répartition possible pour 5 étudiants

### Étudiant 1 — Structure et formulaire
- Initialisation Vue/Vite
- `App.vue`
- `TaskForm.vue`
- ajout des tâches

### Étudiant 2 — Affichage des tâches
- `TaskList.vue`
- `TaskItem.vue`
- `v-for`, `v-if`, `props`

### Étudiant 3 — Modification et suppression
- modification d'une tâche
- suppression
- événements et `emit`

### Étudiant 4 — Filtres et état réactif
- `FilterBar.vue`
- filtres Toutes / À faire / Terminées
- `ref()` et `computed()`

### Étudiant 5 — Sauvegarde et présentation
- `localStorage`
- tests
- responsive design
- README
- captures d'écran et démonstration

## 7. Exemple de commits Git

```text
Initialisation projet Vue 3 + Vite
Ajout formulaire de tâche
Ajout affichage liste des tâches
Ajout modification et suppression
Ajout filtres de tâches
Ajout sauvegarde localStorage
Amélioration interface responsive
Ajout README et captures
```

## 8. Démonstration

Pendant la présentation :

1. Ajouter une tâche.
2. Ajouter plusieurs tâches.
3. Marquer une tâche comme terminée.
4. Afficher uniquement les tâches à faire.
5. Afficher uniquement les tâches terminées.
6. Modifier une tâche.
7. Supprimer une tâche.
8. Actualiser la page et montrer que les données sont conservées grâce à `localStorage`.

## 9. Conformité avec l'évaluation

| Critère | Éléments du projet |
|---|---|
| Fonctionnement | CRUD des tâches + filtres |
| Vue.js | composants, `ref`, `computed`, `watch`, directives |
| Git/GitHub | commits proposés + dépôt collaboratif |
| Qualité du code | composants séparés et noms explicites |
| README | installation, fonctionnalités, organisation et démonstration |

## 10. Dépôt GitHub

Créer le dépôt, puis :

```bash
git init
git add .
git commit -m "Initialisation projet Vue 3"
git branch -M main
git remote add origin VOTRE_URL_GITHUB
git push -u origin main
```

Inviter ensuite les membres du groupe et le compte demandé par l'enseignant comme collaborateurs.
