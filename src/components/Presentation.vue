<script setup>
defineEmits(['close'])
</script>

<template>
  <div class="presentation-page">

    <div class="presentation-header">
      <button class="back-button" @click="$emit('close')">
        ← Retour à l'application
      </button>

      <h1>📚 Présentation du projet</h1>

      <p>
        Mini-projet Vue.js 3 + Vite — Gestionnaire de tâches
      </p>
    </div>

    <!-- Présentation -->
    <section class="presentation-card">
      <h2>🎯 1. Présentation du projet</h2>

      <p>
        Notre projet est une application web de gestion des tâches
        quotidiennes réalisée avec <strong>Vue.js 3</strong> et
        <strong>Vite</strong>.
      </p>

      <p>
        L'objectif est de permettre à l'utilisateur d'ajouter, modifier,
        supprimer et organiser facilement ses tâches.
      </p>
    </section>

    <!-- Technologies -->
    <section class="presentation-card">
      <h2>🛠️ 2. Technologies utilisées</h2>

      <ul>
        <li>Vue.js 3</li>
        <li>Vite</li>
        <li>JavaScript</li>
        <li>HTML5</li>
        <li>CSS3</li>
        <li>LocalStorage</li>
        <li>Git et GitHub</li>
        <li>GitHub Pages</li>
      </ul>
    </section>

    <!-- Fonctionnalités -->
    <section class="presentation-card">
      <h2>✨ 3. Fonctionnalités</h2>

      <ul>
        <li>➕ Ajouter une tâche</li>
        <li>✏️ Modifier une tâche</li>
        <li>🗑️ Supprimer une tâche</li>
        <li>✅ Terminer / remettre à faire</li>
        <li>🔍 Rechercher une tâche</li>
        <li>📋 Filtrer les tâches</li>
        <li>🎯 Gérer les priorités</li>
        <li>📊 Afficher les statistiques</li>
        <li>📈 Afficher la progression</li>
        <li>🌙 Mode sombre / ☀️ mode clair</li>
        <li>💾 Sauvegarde avec LocalStorage</li>
      </ul>
    </section>

    <!-- Vue.js -->
    <section class="presentation-card">
      <h2>💻 4. Concepts Vue.js utilisés</h2>

      <div class="concept">
        <strong>ref()</strong>
        <p>
          Permet de créer des données réactives.
        </p>
      </div>

      <div class="concept">
        <strong>computed()</strong>
        <p>
          Permet de calculer automatiquement certaines valeurs,
          comme le nombre de tâches terminées et la progression.
        </p>
      </div>

      <div class="concept">
        <strong>watch()</strong>
        <p>
          Permet de surveiller les changements et de sauvegarder
          automatiquement les données dans LocalStorage.
        </p>
      </div>

      <div class="concept">
        <strong>v-model</strong>
        <p>
          Permet de lier les champs de formulaire aux données.
        </p>
      </div>

      <div class="concept">
        <strong>v-for</strong>
        <p>
          Permet d'afficher la liste des tâches.
        </p>
      </div>

      <div class="concept">
        <strong>v-if / v-else</strong>
        <p>
          Permettent de gérer les conditions d'affichage.
        </p>
      </div>

      <div class="concept">
        <strong>Props / Emits</strong>
        <p>
          Permettent la communication entre les composants Vue.js.
        </p>
      </div>
    </section>

    <!-- Structure -->
    <section class="presentation-card">
      <h2>📁 5. Structure du projet</h2>

      <pre>
src/
├── components/
│   ├── TaskForm.vue
│   ├── FilterBar.vue
│   └── Presentation.vue
│
├── App.vue
├── main.js
└── style.css
      </pre>
    </section>

    <!-- Membres -->
    <section class="presentation-card">
      <h2>👥 6. Membres du groupe</h2>

      <div class="members">

        <div class="member">
          <span>👨‍💻</span>
          <strong>RAJAOSOLO Manandrazana Eraelien</strong>
          <p>Introduction, présentation et technologies</p>
        </div>

        <div class="member">
          <span>👩‍💻</span>
          <strong>RASOLOFOHARIFARA Marie Rosa</strong>
          <p>Structure et fonctionnalités de base</p>
        </div>

        <div class="member">
          <span>👨‍💻</span>
          <strong>RAKOTOARIMALALA Mitia Mendrika Hankasitrahina</strong>
          <p>Fonctionnalités avancées et démonstration</p>
        </div>

        <div class="member">
          <span>👨‍💻</span>
          <strong>ANDRIAMAMPIHAJA Carmelo</strong>
          <p>Vue.js, LocalStorage, GitHub Pages et conclusion</p>
        </div>

      </div>
    </section>

    <!-- GitHub -->
    <section class="presentation-card github-card">
      <h2>🌐 7. Application en ligne</h2>

      <p>
        Notre application est disponible sur GitHub Pages.
      </p>

      <a
        href="https://manandrazanaeraelien-dev.github.io/l2-gl-2026-groupe-01-todo-app/"
        target="_blank"
        rel="noopener noreferrer"
      >
        🚀 Ouvrir l'application en ligne
      </a>
    </section>

    <!-- Conclusion -->
    <section class="presentation-card">
      <h2>🎓 8. Conclusion</h2>

      <p>
        Ce projet nous a permis de mettre en pratique les principaux
        concepts de Vue.js 3 et de développer une application web
        complète de gestion des tâches.
      </p>

      <p>
        Nous avons également appris à utiliser LocalStorage, Git,
        GitHub et GitHub Pages.
      </p>

      <h3>🙏 Merci pour votre attention !</h3>
    </section>

  </div>
</template>