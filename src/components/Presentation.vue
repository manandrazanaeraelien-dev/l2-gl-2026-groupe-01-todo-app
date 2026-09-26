<script setup>
defineEmits(['close'])

const membres = [
  {
    nom: 'RAJAOSOLO Manandrazana Eraelien',
    role: 'Chef de projet / Lead Dev',
    discours: "Bonjour à tous. Je vais vous présenter la structure globale de notre mini-projet réalisé avec Vue.js 3 et Vite. Il s'agit d'une application de gestion de tâches (ToDo App). Pour ma part, j'ai géré l'architecture générale dans App.vue, la réactivité des données, la persistance automatique dans le localStorage, ainsi que la configuration du dépôt GitHub et l'invitation de notre collaborateur @GasyCoder.",
    etapes: [
      {
        titre: "Introduction, présentation et technologies",
        details: "Présentation des objectifs du projet Todo App, du groupe L2 GL 01 et du choix de la stack moderne Vue 3 + Vite."
      },
      {
        titre: "Architecture globale (App.vue) & réactivité",
        details: "Mise en place de la structure racine App.vue, gestion de l'état réactif principal des tâches et persistance dynamique avec LocalStorage."
      },
      {
        titre: "Configuration GitHub & GitHub Pages (deploy.yml)",
        details: "Création du dépôt Git, invitation des collaborateurs et mise en place du déploiement automatisé via GitHub Actions."
      }
    ]
  },
  {
    nom: 'RASOLOFOHARIFARA Marie Rosa',
    role: 'Développeuse Frontend',
    discours: "Bonjour. De mon côté, je me suis occupée de la création du composant TaskForm.vue pour l'ajout des nouvelles tâches. J'ai utilisé la directive v-model pour la liaison automatique des données et les événements emit pour transmettre la nouvelle tâche au composant parent. J'ai également participé à la mise en place de la barre de filtrage dans FilterBar.vue.",
    etapes: [
      {
        titre: "Structure et fonctionnalités de base",
        details: "Définition de l'interface utilisateur initiale et structuration logique des composants du formulaire."
      },
      {
        titre: "Création du composant TaskForm.vue (v-model, emit)",
        details: "Implémentation de la saisie avec liaison bidirectionnelle v-model et émission d'événements @add-task vers le parent."
      },
      {
        titre: "Intégration de FilterBar.vue",
        details: "Conception du composant de navigation par filtres pour basculer facilement entre les vues de tâches."
      }
    ]
  },
  {
    nom: 'RAKOTOARIMALALA Mitia Mendrika Hankasitrahina',
    role: 'Développeur Frontend & UI',
    discours: "Bonjour. J'ai pris en charge la création des composants TaskList.vue et TaskItem.vue pour l'affichage dynamique des tâches avec la directive v-for. J'ai aussi implémenté les fonctionnalités de modification, de suppression et d'archivage des tâches, tout en travaillant sur le style CSS pour offrir une interface claire et agréable.",
    etapes: [
      {
        titre: "Composants TaskList.vue et TaskItem.vue (v-for)",
        details: "Rendu dynamique et performant de la liste des tâches avec la directive v-for et passage des props."
      },
      {
        titre: "Édition, suppression de tâches et gestion du statut",
        details: "Mise en place du mode modification en ligne, de la suppression individuelle et de la coche d'achèvement."
      },
      {
        titre: "Conception graphique et styles CSS",
        details: "Habillage CSS complet avec responsive design et intégration fluide du mode clair / sombre."
      }
    ]
  },
  {
    nom: 'ANDRIAMAMPIHAJA Carmelo',
    role: 'Développeur Fullstack',
    discours: "Bonjour. Ma contribution a porté sur le développement du système de recherche en temps réel et le filtrage des tâches par statut (Toutes, À faire, Terminées). J'ai utilisé les propriétés calculées computed() pour calculer automatiquement le pourcentage de progression et les statistiques. J'ai également effectué les tests d'utilisation pour vérifier la persistance dans le localStorage.",
    etapes: [
      {
        titre: "Recherche en temps réel et filtrage par statut",
        details: "Création de la barre de recherche textuelle dynamique filtrant les tâches instantanément à la saisie."
      },
      {
        titre: "Calcul des statistiques et progression (computed)",
        details: "Utilisation des propriétés réactives computed() pour mettre à jour automatiquement la barre de progression et le compteur."
      },
      {
        titre: "Tests, recette et vérification LocalStorage",
        details: "Validation du comportement de l'application après rafraîchissement et vérification de la publication sur GitHub Pages."
      }
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
        <h2>👥 6. Membres du groupe</h2>
        
        <div class="members-grid">
          <div 
            v-for="(m, index) in membres" 
            :key="index" 
            class="member-card"
          >
            <!-- Avatar -->
            <div class="avatar">👨‍💻</div>

            <!-- Nom et Role -->
            <div class="member-header">
              <h3>{{ m.nom }}</h3>
              <span class="role-badge">{{ m.role }}</span>
            </div>

            <!-- Discours oral -->
            <div class="speech-box">
              <strong class="speech-title">🎙️ Explication orale :</strong>
              <p class="speech-text">"{{ m.discours }}"</p>
            </div>

            <!-- Etapes / Taches avec explications -->
            <div class="etapes-container">
              <div 
                v-for="(etape, i) in m.etapes" 
                :key="i" 
                class="etape-item"
              >
                <div class="etape-title">- {{ etape.titre }}</div>
                <div class="etape-details">{{ etape.details }}</div>
              </div>
            </div>
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
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: #1f2937;
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
  background: #ffffff;
  border: 1px solid #e5e7eb;
  border-radius: 12px;
  padding: 20px;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
  display: flex;
  flex-direction: column;
}

.avatar {
  font-size: 2.2rem;
  margin-bottom: 6px;
}

.member-header h3 {
  margin: 0;
  font-size: 1.1rem;
  color: #111827;
  font-weight: 700;
}

.role-badge {
  display: inline-block;
  font-size: 0.8rem;
  color: #4f46e5;
  font-weight: 600;
  margin-top: 2px;
  margin-bottom: 12px;
}

.speech-box {
  background: #f8fafc;
  border-left: 4px solid #6366f1;
  padding: 12px;
  border-radius: 6px;
  margin-bottom: 16px;
}

.speech-title {
  display: block;
  font-size: 0.88rem;
  color: #312e81;
  margin-bottom: 4px;
}

.speech-text {
  margin: 0;
  font-style: italic;
  font-size: 0.85rem;
  color: #334155;
  line-height: 1.45;
}

.etapes-container {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.etape-item {
  background: #f9fafb;
  padding: 8px 12px;
  border-radius: 6px;
  border: 1px solid #f3f4f6;
}

.etape-title {
  font-weight: 600;
  font-size: 0.88rem;
  color: #1f2937;
  margin-bottom: 2px;
}

.etape-details {
  font-size: 0.82rem;
  color: #6b7280;
  line-height: 1.35;
  padding-left: 10px;
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