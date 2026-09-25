# 🎤 PRÉSENTATION ORALE
# Gestionnaire de tâches — ToDo App

## Mini-projet — Introduction aux Frameworks JavaScript

**Technologie principale : Vue.js 3 + Vite**

### 👥 Membres du groupe

- **RAJAOSOLO Manandrazana Eraelien**
- **RASOLOFOHARIFARA Marie Rosa**

---

# 👤 PARTIE 1 — RAJAOSOLO Manandrazana Eraelien

## 1. Introduction

Bonjour Madame / Monsieur.

Nous allons vous présenter notre mini-projet réalisé dans le cadre du cours **Introduction aux Frameworks JavaScript**.

Notre projet s'intitule **« Gestionnaire de tâches »**, ou **ToDo App**.

Nous avons réalisé cette application avec **Vue.js 3** et **Vite**.

Les membres de notre groupe sont :

- RAJAOSOLO Manandrazana Eraelien
- RASOLOFOHARIFARA Marie Rosa

---

## 2. Objectif du projet

L'objectif de notre projet est de créer une application web permettant à un utilisateur de **gérer facilement ses tâches quotidiennes**.

L'utilisateur peut :

- ajouter une tâche ;
- modifier une tâche ;
- supprimer une tâche ;
- marquer une tâche comme terminée.

Nous avons également ajouté plusieurs fonctionnalités supplémentaires comme :

- la recherche ;
- les filtres ;
- les priorités ;
- les statistiques ;
- la progression ;
- le mode sombre ;
- la sauvegarde avec LocalStorage.

---

## 3. Technologies utilisées

Pour réaliser cette application, nous avons utilisé :

- **Vue.js 3**
- **Vite**
- **JavaScript**
- **HTML5**
- **CSS3**
- **LocalStorage**
- **Git**
- **GitHub**

Vue.js permet de créer une interface utilisateur dynamique et réactive.

Vite nous permet de créer et d'exécuter rapidement notre projet Vue.js.

---

# 👤 PARTIE 2 — RASOLOFOHARIFARA Marie Rosa

## 4. Fonctionnalités principales

Notre application possède plusieurs fonctionnalités.

Premièrement, l'utilisateur peut **ajouter une tâche**.

Deuxièmement, il peut **modifier une tâche existante**.

Il peut également **supprimer une tâche**.

Une tâche peut être **marquée comme terminée** ou redevenir non terminée.

Nous avons également ajouté un système de **priorité** avec trois niveaux :

- 🔴 Haute
- 🟠 Moyenne
- 🟢 Basse

L'utilisateur peut aussi rechercher une tâche et utiliser les filtres pour afficher les tâches selon leur état.

---

## 5. Recherche et filtres

L'application possède une barre de recherche.

Elle permet à l'utilisateur de rechercher rapidement une tâche.

Nous avons également plusieurs filtres :

- **Toutes**
- **En cours**
- **Terminées**

Cela permet de retrouver facilement les tâches selon leur état.

---

## 6. Statistiques et progression

L'application affiche également des statistiques.

Nous pouvons voir :

- le nombre total de tâches ;
- le nombre de tâches terminées ;
- le nombre de tâches restantes.

Une **barre de progression** permet également de visualiser l'avancement des tâches.

Les statistiques sont mises à jour automatiquement lorsque l'utilisateur modifie l'état des tâches.

---

## 7. Mode sombre

Nous avons également ajouté un **mode sombre**.

L'utilisateur peut passer du mode clair au mode sombre grâce au bouton prévu dans l'interface.

Cette fonctionnalité permet d'améliorer le confort d'utilisation de l'application.

---

# 👤 PARTIE 1 — RAJAOSOLO Manandrazana Eraelien

## 8. Utilisation de Vue.js

Dans notre projet, nous avons utilisé plusieurs notions importantes de Vue.js.

Nous avons utilisé **ref()** pour gérer les données réactives.

Nous avons utilisé **computed()** pour calculer automatiquement certaines informations comme les tâches filtrées et les statistiques.

Nous avons utilisé **watch()** pour surveiller les changements et sauvegarder les données dans le LocalStorage.

Nous avons également utilisé :

- **v-model** pour les formulaires ;
- **v-for** pour afficher les tâches ;
- **v-if** pour le rendu conditionnel ;
- les événements comme **@click** et **@submit** ;
- les **props** ;
- les **emits**.

---

## 9. Organisation des composants

Nous avons organisé notre application en plusieurs composants afin d'avoir un code plus clair et plus facile à maintenir.

Le composant principal est :

### App.vue

Il gère notamment :

- les tâches ;
- les filtres ;
- la recherche ;
- les statistiques ;
- le mode sombre ;
- le LocalStorage ;
- les différentes actions.

Nous avons également :

### TaskForm.vue

Ce composant permet d'ajouter une nouvelle tâche et de choisir sa priorité.

### TaskList.vue

Ce composant permet d'afficher la liste des tâches.

### TaskItem.vue

Ce composant représente une tâche individuelle.

### FilterBar.vue

Ce composant permet de gérer les filtres.

---

# 👤 PARTIE 2 — RASOLOFOHARIFARA Marie Rosa

## 10. Sauvegarde des données

Pour éviter de perdre les tâches après avoir actualisé la page, nous avons utilisé le **LocalStorage du navigateur**.

Les tâches sont automatiquement sauvegardées lorsqu'elles sont modifiées.

Ainsi, après un rafraîchissement de la page, les tâches restent disponibles.

---

# 🎬 11. Démonstration de l'application

Nous allons maintenant faire une petite démonstration de notre application.

### Étape 1 — Ajouter une tâche

Je vais commencer par ajouter une nouvelle tâche.

Par exemple :

**Faire les exercices de JavaScript**

Je choisis ensuite une priorité, par exemple :

**🔴 Haute**

Puis je clique sur :

**+ Ajouter**

---

### Étape 2 — Modifier une tâche

Maintenant, je vais modifier cette tâche.

Je clique sur **Modifier**.

Je peux changer le nom de la tâche puis enregistrer la modification.

---

### Étape 3 — Terminer une tâche

Je vais maintenant marquer la tâche comme terminée.

La tâche change alors d'état.

---

### Étape 4 — Utiliser les filtres

Je peux maintenant utiliser les filtres.

Par exemple, je sélectionne **Terminées** pour afficher uniquement les tâches terminées.

---

### Étape 5 — Rechercher une tâche

Je peux également utiliser la barre de recherche.

Je saisis le nom ou une partie du nom d'une tâche.

L'application affiche automatiquement les résultats correspondants.

---

### Étape 6 — Vérifier les statistiques

Nous pouvons constater que les statistiques sont automatiquement mises à jour.

Le nombre de tâches terminées et restantes change selon l'état des tâches.

La barre de progression change également.

---

### Étape 7 — Activer le mode sombre

Enfin, je vais activer le mode sombre.

L'interface passe du mode clair au mode sombre.

---

# 👤 PARTIE 1 — RAJAOSOLO Manandrazana Eraelien

## 12. Git et GitHub

Pour gérer notre code source, nous avons utilisé **Git** et **GitHub**.

Nous avons créé un repository GitHub pour notre projet.

Nous avons effectué plusieurs commits afin de suivre les différentes étapes du développement.

Git nous permet de conserver l'historique des modifications.

GitHub nous permet également d'héberger et de partager notre code source.

---

## 13. Repository du projet

Notre projet est disponible sur GitHub :

**l2-gl-2026-groupe-01-todo-app**

Repository :

https://github.com/manandrazanaeraelien-dev/l2-gl-2026-groupe-01-todo-app

---

# 👤 PARTIE 2 — RASOLOFOHARIFARA Marie Rosa

## 14. Contribution des membres

Pour la réalisation du projet, nous avons travaillé ensemble sur les différentes parties de l'application.

### RAJAOSOLO Manandrazana Eraelien

Participation au :

- développement de la structure de l'application ;
- développement des fonctionnalités ;
- intégration de Vue.js ;
- gestion de Git et GitHub ;
- tests de l'application.

### RASOLOFOHARIFARA Marie Rosa

Participation au :

- développement des fonctionnalités ;
- interface utilisateur ;
- tests de l'application ;
- vérification des fonctionnalités ;
- présentation du projet.

Nous avons collaboré pour obtenir une application fonctionnelle et organisée.

---

# 👥 PARTIE FINALE — ENSEMBLE

## 15. Conclusion

Pour conclure, ce projet nous a permis de mettre en pratique les principales notions de **Vue.js 3**.

Nous avons appris à :

- créer des composants ;
- gérer les données réactives ;
- utiliser les formulaires ;
- gérer les événements ;
- utiliser les filtres ;
- calculer les statistiques ;
- utiliser le LocalStorage ;
- utiliser Git et GitHub.

Notre application permet donc de gérer les tâches quotidiennes de manière simple, claire et interactive.

---

## 🙏 Remerciements

**Nous vous remercions pour votre attention.**

**Avez-vous des questions ?**
