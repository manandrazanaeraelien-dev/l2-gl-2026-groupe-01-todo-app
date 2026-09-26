<script setup>
defineEmits(['close'])

const membres = [
  {
    nom: 'RAJAOSOLO Manandrazana Eraelien',
    role: 'Chef de projet / Lead Dev',
    discours: "Bonjour à tous. Je vais vous présenter la structure globale de notre mini-projet réalisé avec Vue.js 3 et Vite. Il s'agit d'une application de gestion de tâches (ToDo App). Pour ma part, j'ai géré l'architecture générale dans App.vue, la réactivité des données, la persistance automatique dans le localStorage, ainsi que la configuration du dépôt GitHub et l'invitation de notre collaborateur @GasyCoder.",
    taches: [
      'Introduction, présentation et technologies',
      'Architecture globale (App.vue) & réactivité',
      'Configuration GitHub & GitHub Pages (deploy.yml)'
    ]
  },
  {
    nom: 'RASOLOFOHARIFARA Marie Rosa',
    role: 'Développeuse Frontend',
    discours: "Bonjour. De mon côté, je me suis occupée de la création du composant TaskForm.vue pour l'ajout des nouvelles tâches. J'ai utilisé la directive v-model pour la liaison automatique des données et les événements emit pour transmettre la nouvelle tâche au composant parent. J'ai également participé à la mise en place de la barre de filtrage dans FilterBar.vue.",
    taches: [
      'Structure et fonctionnalités de base',
      'Création du composant TaskForm.vue (v-model, emit)',
      'Intégration de FilterBar.vue'
    ]
  },
  {
    nom: 'RAKOTOARIMALALA Mitia Mendrika Hankasitrahina',
    role: 'Développeur Frontend & UI',
    discours: "Bonjour. J'ai pris en charge la création des composants TaskList.vue et TaskItem.vue pour l'affichage dynamique des tâches avec la directive v-for. J'ai aussi implémenté les fonctionnalités de modification, de suppression et d'archivage des tâches, tout en travaillant sur le style CSS pour offrir une interface claire et agréable.",
    taches: [
      'Fonctionnalités avancées et démonstration',
      'Composants TaskList.vue et TaskItem.vue (v-for)',
      'Édition, suppression de tâches et styles CSS'
    ]
  },
  {
    nom: 'ANDRIAMAMPIHAJA Carmelo',
    role: 'Développeur Fullstack',
    discours: "Bonjour. Ma contribution a porté sur le développement du système de recherche en temps réel et le filtrage des tâches par statut (Toutes, À faire, Terminées). J'ai utilisé les propriétés calculées computed() pour calculer automatiquement le pourcentage de progression et les statistiques. J'ai également effectué les tests d'utilisation pour vérifier la persistance dans le localStorage.",
    taches: [
      'Vue.js, LocalStorage, GitHub Pages et conclusion',
      'Recherche en temps réel et filtrage par statut',
      'Calcul des statistiques et progression (computed)'
    ]
  }
]
</script>

<template>
  <div class="presentation-page">
    <!-- Header -->
    <div class="presentation-header">
      <button class="back-button" @click="$emit('close')">
        ⬅️ Retour à l'application
      </button>
      <h1>📚 Présentation du Projet — Groupe 01</h1>
    </div>

    <div class="container">
      <!-- Section Membres -->
      <section class="section">
        <h2>👥 6. Membres du groupe et Discours Orale</h2>
        
        <div class="members-grid">
          <div 
            v-for="(m, index) in membres" 
            :key="index" 
            class="member-card"
          >
            <div class="member-header">
              <span class="avatar">👨‍💻</span>
              <div>
                <h3>{{ m.nom }}</h3>
                <span class="badge">{{ m.role }}</span>
              </div>
            </div>

            <!-- Explication / Discours orale -->
            <div class="speech-box">
              <strong>🎙️ Explication orale :</strong>
              <p><em>"{{ m.discours }}"</em></p>
            </div>
            
            <ul class="task-list">
              <li v-for="(tache, i) in m.taches" :key="i">
                {{ tache }}
              </li>
            </ul>
          </div>
        </div>
      </section>

      <!-- Section App en ligne -->
      <section class="section online-app">
        <h2>🌐 7. Application en ligne</h2>
        <p>Notre application est disponible sur GitHub Pages.</p>
        <a 
          href="https://manandrazanaeraelien-dev.github.io/l2-gl-2026-groupe-01-todo-app/" 
          target="_blank" 
          class="app-link-btn"
        >
          🚀 Ouvrir l'application en ligne
        </a>
      </section>
    </div>
  </div>
</template>

<style scoped>
.presentation-page {
  padding: 20px;
  max-width: 1100px;
  margin: 0 auto;
  font-family: Arial, sans-serif;
}

.presentation-header {
  display: flex;
  align-items: center;
  gap: 20px;
  margin-bottom: 25px;
}

.back-button {
  padding: 8px 16px;
  background-color: #4b5563;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-weight: bold;
}

.back-button:hover {
  background-color: #374151;
}

.members-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 20px;
  margin-top: 15px;
}

.member-card {
  background: #f9fafb;
  border: 1px solid #e5e7eb;
  border-radius: 10px;
  padding: 18px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.member-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 12px;
}

.avatar {
  font-size: 2rem;
}

.member-header h3 {
  margin: 0;
  font-size: 1.05rem;
  color: #1f2937;
}

.badge {
  display: inline-block;
  font-size: 0.75rem;
  background: #e0e7ff;
  color: #3730a3;
  padding: 2px 8px;
  border-radius: 12px;
  margin-top: 4px;
}

.speech-box {
  background: #ffffff;
  border-left: 4px solid #6366f1;
  padding: 10px;
  border-radius: 6px;
  margin-bottom: 12px;
  font-size: 0.88rem;
  color: #374151;
}

.speech-box strong {
  color: #4f46e5;
}

.speech-box p {
  margin: 5px 0 0 0;
  line-height: 1.4;
}

.task-list {
  margin: 0;
  padding-left: 20px;
  color: #4b5563;
  font-size: 0.88rem;
  line-height: 1.5;
}

.task-list li {
  margin-bottom: 4px;
}

.online-app {
  margin-top: 30px;
  background: #f0fdf4;
  border: 1px solid #bbf7d0;
  padding: 20px;
  border-radius: 10px;
  text-align: center;
}

.app-link-btn {
  display: inline-block;
  margin-top: 10px;
  padding: 10px 20px;
  background: #16a34a;
  color: white;
  text-decoration: none;
  border-radius: 6px;
  font-weight: bold;
}

.app-link-btn:hover {
  background: #15803d;
}
</style>