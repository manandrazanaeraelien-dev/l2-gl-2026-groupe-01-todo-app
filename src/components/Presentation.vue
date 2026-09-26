<script setup>
defineEmits(['close'])
</script>

<template>
  <div class="presentation-page">

    <!-- =========================
         EN-TÊTE
    ========================== -->

    <div class="presentation-header">

      <button
        class="back-button"
        @click="$emit('close')"
      >
        ← Retour à l'application
      </button>

      <h1>
        📚 Présentation du projet
      </h1>

      <p>
        Mini-projet Vue.js 3 + Vite — Gestionnaire de tâches
      </p>

      <p class="presentation-intro">
        Présentation complète du projet réalisée par les membres
        du groupe 01.
      </p>

    </div>


    <!-- =========================
         1. PRESENTATION
    ========================== -->

    <section class="presentation-card">

      <h2>
        🎯 1. Présentation du projet
      </h2>

      <p>
        Notre projet est une application web de gestion des tâches
        quotidiennes réalisée avec <strong>Vue.js 3</strong> et
        <strong>Vite</strong>.
      </p>

      <p>
        Cette application permet à l'utilisateur de créer une liste
        de tâches, de les organiser, de les modifier, de les supprimer
        et de suivre leur état d'avancement.
      </p>

      <p>
        L'objectif principal de ce mini-projet est de mettre en pratique
        les concepts fondamentaux d'un framework JavaScript moderne,
        notamment la réactivité, les composants, les événements,
        les propriétés, les émissions d'événements et la gestion
        des données.
      </p>

      <h3>
        🎓 Objectifs pédagogiques
      </h3>

      <ul>
        <li>
          Comprendre le fonctionnement de Vue.js 3.
        </li>

        <li>
          Utiliser des composants réutilisables.
        </li>

        <li>
          Manipuler des données réactives.
        </li>

        <li>
          Utiliser les directives Vue.js.
        </li>

        <li>
          Gérer les événements utilisateur.
        </li>

        <li>
          Sauvegarder les données avec LocalStorage.
        </li>

        <li>
          Utiliser Git et GitHub pour gérer le projet.
        </li>

        <li>
          Déployer l'application avec GitHub Pages.
        </li>
      </ul>

    </section>


    <!-- =========================
         2. TECHNOLOGIES
    ========================== -->

    <section class="presentation-card">

      <h2>
        🛠️ 2. Technologies utilisées
      </h2>

      <div class="technology-list">

        <div class="technology-item">
          <strong>🟢 Vue.js 3</strong>
          <p>
            Framework JavaScript utilisé pour créer l'interface
            interactive de l'application.
          </p>
        </div>

        <div class="technology-item">
          <strong>⚡ Vite</strong>
          <p>
            Outil utilisé pour créer le projet, lancer le serveur
            de développement et construire l'application.
          </p>
        </div>

        <div class="technology-item">
          <strong>🟨 JavaScript</strong>
          <p>
            Langage utilisé pour programmer la logique de
            l'application.
          </p>
        </div>

        <div class="technology-item">
          <strong>🌐 HTML5</strong>
          <p>
            Utilisé pour structurer les différents éléments
            de l'interface.
          </p>
        </div>

        <div class="technology-item">
          <strong>🎨 CSS3</strong>
          <p>
            Utilisé pour créer le design, les couleurs,
            les espacements, les boutons et le responsive design.
          </p>
        </div>

        <div class="technology-item">
          <strong>💾 LocalStorage</strong>
          <p>
            Utilisé pour conserver les tâches et les préférences
            de l'utilisateur dans le navigateur.
          </p>
        </div>

        <div class="technology-item">
          <strong>🐙 Git / GitHub</strong>
          <p>
            Utilisés pour sauvegarder, versionner et partager
            le projet.
          </p>
        </div>

        <div class="technology-item">
          <strong>🌐 GitHub Pages</strong>
          <p>
            Utilisé pour mettre l'application en ligne.
          </p>
        </div>

      </div>

    </section>


    <!-- =========================
         3. FONCTIONNALITES
    ========================== -->

    <section class="presentation-card">

      <h2>
        ✨ 3. Fonctionnalités de l'application
      </h2>

      <div class="feature-list">

        <div class="feature-item">
          <strong>➕ Ajouter une tâche</strong>

          <p>
            L'utilisateur peut saisir le nom d'une tâche et choisir
            son niveau de priorité : haute, moyenne ou basse.
          </p>
        </div>


        <div class="feature-item">
          <strong>✏️ Modifier une tâche</strong>

          <p>
            L'utilisateur peut modifier le titre et la priorité
            d'une tâche existante.
          </p>
        </div>


        <div class="feature-item">
          <strong>🗑️ Supprimer une tâche</strong>

          <p>
            Une tâche peut être supprimée après confirmation
            de l'utilisateur.
          </p>
        </div>


        <div class="feature-item">
          <strong>✅ Terminer une tâche</strong>

          <p>
            L'utilisateur peut marquer une tâche comme terminée
            ou la remettre à faire.
          </p>
        </div>


        <div class="feature-item">
          <strong>🔍 Rechercher une tâche</strong>

          <p>
            La recherche permet de retrouver rapidement une tâche
            grâce à son titre.
          </p>
        </div>


        <div class="feature-item">
          <strong>📋 Filtrer les tâches</strong>

          <p>
            Trois filtres sont disponibles :
            toutes les tâches, les tâches à faire et les tâches
            terminées.
          </p>
        </div>


        <div class="feature-item">
          <strong>🎯 Priorités</strong>

          <p>
            Chaque tâche peut avoir une priorité haute, moyenne
            ou basse.
          </p>
        </div>


        <div class="feature-item">
          <strong>📊 Statistiques</strong>

          <p>
            L'application affiche le nombre total de tâches,
            le nombre de tâches à faire et le nombre de tâches
            terminées.
          </p>
        </div>


        <div class="feature-item">
          <strong>📈 Progression</strong>

          <p>
            Une barre de progression indique le pourcentage
            de tâches terminées.
          </p>
        </div>


        <div class="feature-item">
          <strong>🌙 Mode sombre / ☀️ Mode clair</strong>

          <p>
            L'utilisateur peut changer l'apparence de l'application
            entre le mode clair et le mode sombre.
          </p>
        </div>


        <div class="feature-item">
          <strong>💾 Sauvegarde automatique</strong>

          <p>
            Les tâches sont automatiquement enregistrées dans
            le LocalStorage du navigateur.
          </p>
        </div>


        <div class="feature-item">
          <strong>↩️ Annulation de suppression</strong>

          <p>
            Les tâches terminées supprimées peuvent être restaurées
            grâce à l'action d'annulation.
          </p>
        </div>

      </div>

    </section>


    <!-- =========================
         4. CONCEPTS VUE.JS
    ========================== -->

    <section class="presentation-card">

      <h2>
        💻 4. Concepts Vue.js utilisés
      </h2>


      <div class="concept">

        <strong>1. ref()</strong>

        <p>
          <strong>ref()</strong> permet de créer une donnée réactive.
          Lorsque sa valeur change, Vue.js met automatiquement
          à jour l'interface.
        </p>

        <p>
          Dans notre projet, nous l'utilisons pour gérer par exemple
          le mode sombre, les tâches, la recherche et les notifications.
        </p>

      </div>


      <div class="concept">

        <strong>2. computed()</strong>

        <p>
          <strong>computed()</strong> permet de calculer
          automatiquement une valeur à partir des données réactives.
        </p>

        <p>
          Nous l'utilisons pour calculer le nombre total de tâches,
          le nombre de tâches terminées, les tâches restantes et
          le pourcentage de progression.
        </p>

      </div>


      <div class="concept">

        <strong>3. watch()</strong>

        <p>
          <strong>watch()</strong> permet de surveiller les changements
          d'une donnée.
        </p>

        <p>
          Dans notre application, il permet de sauvegarder
          automatiquement les tâches dans le LocalStorage.
        </p>

      </div>


      <div class="concept">

        <strong>4. v-model</strong>

        <p>
          <strong>v-model</strong> permet de créer une liaison
          entre les champs de formulaire et les données Vue.js.
        </p>

        <p>
          Nous l'utilisons pour le champ de recherche, le titre
          d'une tâche et la sélection de priorité.
        </p>

      </div>


      <div class="concept">

        <strong>5. v-for</strong>

        <p>
          <strong>v-for</strong> permet de parcourir une liste
          et d'afficher plusieurs éléments.
        </p>

        <p>
          Dans notre projet, il permet d'afficher toutes les tâches
          présentes dans la liste.
        </p>

      </div>


      <div class="concept">

        <strong>6. v-if / v-else</strong>

        <p>
          Ces directives permettent d'afficher ou de cacher
          certains éléments selon une condition.
        </p>

        <p>
          Par exemple, nous affichons un message lorsqu'aucune tâche
          n'est trouvée et nous affichons également le formulaire
          de modification uniquement lorsqu'une tâche est en mode édition.
        </p>

      </div>


      <div class="concept">

        <strong>7. @click / @submit / @keyup</strong>

        <p>
          Ces événements permettent de réagir aux actions
          de l'utilisateur.
        </p>

        <p>
          Par exemple, <strong>@click</strong> est utilisé pour
          les boutons, <strong>@submit</strong> pour le formulaire
          d'ajout et <strong>@keyup.enter</strong> pour enregistrer
          une modification avec la touche Entrée.
        </p>

      </div>


      <div class="concept">

        <strong>8. Props</strong>

        <p>
          Les <strong>props</strong> permettent de transmettre
          des informations d'un composant parent vers un composant enfant.
        </p>

        <p>
          Dans notre projet, App.vue transmet par exemple
          le filtre actuel à FilterBar.vue.
        </p>

      </div>


      <div class="concept">

        <strong>9. Emits</strong>

        <p>
          Les <strong>emits</strong> permettent à un composant enfant
          d'envoyer un événement vers son composant parent.
        </p>

        <p>
          Par exemple, TaskForm.vue émet l'événement
          <strong>add-task</strong> lorsqu'une nouvelle tâche est ajoutée.
        </p>

      </div>

    </section>


    <!-- =========================
         5. STRUCTURE
    ========================== -->

    <section class="presentation-card">

      <h2>
        📁 5. Structure du projet
      </h2>

      <pre>
src/
│
├── components/
│   ├── TaskForm.vue
│   ├── FilterBar.vue
│   └── Presentation.vue
│
├── App.vue
├── main.js
└── style.css

index.html
package.json
vite.config.js
README.md
      </pre>

      <div class="structure-explanation">

        <p>
          <strong>App.vue :</strong>
          composant principal qui contient la logique générale
          de l'application.
        </p>

        <p>
          <strong>TaskForm.vue :</strong>
          composant responsable du formulaire d'ajout d'une tâche.
        </p>

        <p>
          <strong>FilterBar.vue :</strong>
          composant responsable des filtres.
        </p>

        <p>
          <strong>Presentation.vue :</strong>
          composant qui contient la présentation complète du projet.
        </p>

        <p>
          <strong>main.js :</strong>
          point d'entrée de l'application Vue.js.
        </p>

        <p>
          <strong>style.css :</strong>
          contient le design et la mise en forme de l'application.
        </p>

      </div>

    </section>


    <!-- =========================
         6. MEMBRE 1
    ========================== -->

    <section class="presentation-card member-presentation">

      <h2>
        👨‍💻 6. Membre 1 — RAJAOSOLO Manandrazana Eraelien
      </h2>

      <div class="member-role">

        <h3>
          🎤 Partie : Introduction, présentation et technologies
        </h3>

        <p>
          Le premier membre présente le contexte général du projet,
          les objectifs et les technologies utilisées.
        </p>

      </div>


      <div class="oral-section">

        <h3>
          🗣️ Texte à présenter à l'oral
        </h3>

        <p>
          « Bonjour à tous. Nous allons vous présenter notre
          mini-projet intitulé Gestionnaire de tâches.
        </p>

        <p>
          Il s'agit d'une application web réalisée avec Vue.js 3
          et Vite. L'objectif de notre projet est de permettre
          à un utilisateur de gérer facilement ses tâches quotidiennes.
        </p>

        <p>
          Avec notre application, l'utilisateur peut ajouter,
          modifier, supprimer et terminer des tâches.
          Il peut également rechercher une tâche, utiliser des filtres,
          définir une priorité et suivre sa progression.
        </p>

        <p>
          Pour réaliser ce projet, nous avons utilisé plusieurs
          technologies : Vue.js 3 pour l'interface interactive,
          Vite pour le développement, JavaScript pour la logique,
          HTML5 et CSS3 pour la structure et le design.
        </p>

        <p>
          Nous avons également utilisé LocalStorage pour conserver
          les données dans le navigateur, puis Git et GitHub
          pour gérer le projet et GitHub Pages pour le déploiement.
          »
        </p>

      </div>


      <div class="demo-section">

        <h3>
          🖥️ Démonstration du membre 1
        </h3>

        <ol>
          <li>Présenter le titre de l'application.</li>
          <li>Expliquer l'objectif du projet.</li>
          <li>Présenter les technologies utilisées.</li>
          <li>Montrer l'interface générale.</li>
          <li>Présenter rapidement les différentes parties de l'application.</li>
        </ol>

      </div>

    </section>


    <!-- =========================
         7. MEMBRE 2
    ========================== -->

    <section class="presentation-card member-presentation">

      <h2>
        👩‍💻 7. Membre 2 — RASOLOFOHARIFARA Marie Rosa
      </h2>

      <div class="member-role">

        <h3>
          🎤 Partie : Structure et fonctionnalités de base
        </h3>

        <p>
          Le deuxième membre explique la structure du projet
          ainsi que les fonctionnalités principales de gestion
          des tâches.
        </p>

      </div>


      <div class="oral-section">

        <h3>
          🗣️ Texte à présenter à l'oral
        </h3>

        <p>
          « Je vais maintenant présenter la structure de notre projet
          ainsi que les principales fonctionnalités.
        </p>

        <p>
          Notre projet est organisé en plusieurs fichiers et composants.
          App.vue est le composant principal. TaskForm.vue permet
          d'ajouter une nouvelle tâche et FilterBar.vue permet
          de filtrer les tâches.
        </p>

        <p>
          L'utilisateur peut commencer par ajouter une tâche.
          Il saisit son titre et choisit éventuellement une priorité.
          Lorsqu'il valide le formulaire, la nouvelle tâche apparaît
          dans la liste.
        </p>

        <p>
          Il est également possible de modifier une tâche.
          L'utilisateur peut changer son titre et sa priorité.
        </p>

        <p>
          Une tâche peut aussi être marquée comme terminée.
          Elle peut ensuite être remise à faire.
        </p>

        <p>
          Enfin, l'utilisateur peut supprimer une tâche.
          Une confirmation est demandée avant la suppression.
          »
        </p>

      </div>


      <div class="demo-section">

        <h3>
          🖥️ Démonstration du membre 2
        </h3>

        <ol>
          <li>Ajouter une nouvelle tâche.</li>
          <li>Choisir une priorité.</li>
          <li>Modifier une tâche.</li>
          <li>Terminer une tâche.</li>
          <li>Remettre une tâche à faire.</li>
          <li>Supprimer une tâche.</li>
        </ol>

      </div>

    </section>


    <!-- =========================
         8. MEMBRE 3
    ========================== -->

    <section class="presentation-card member-presentation">

      <h2>
        👨‍💻 8. Membre 3 — RAKOTOARIMALALA Mitia Mendrika Hankasitrahina
      </h2>

      <div class="member-role">

        <h3>
          🎤 Partie : Fonctionnalités avancées et démonstration
        </h3>

        <p>
          Le troisième membre présente les fonctionnalités avancées
          qui permettent d'améliorer l'utilisation de l'application.
        </p>

      </div>


      <div class="oral-section">

        <h3>
          🗣️ Texte à présenter à l'oral
        </h3>

        <p>
          « Je vais présenter maintenant les fonctionnalités avancées
          de notre application.
        </p>

        <p>
          Tout d'abord, nous avons ajouté une fonction de recherche.
          Elle permet à l'utilisateur de retrouver rapidement
          une tâche en saisissant un mot dans la barre de recherche.
        </p>

        <p>
          Nous avons également créé trois filtres :
          toutes les tâches, les tâches à faire et les tâches terminées.
          Cela permet de mieux organiser la liste.
        </p>

        <p>
          Notre application possède également un système de priorité.
          Une tâche peut être définie comme haute, moyenne ou basse.
        </p>

        <p>
          Nous avons ajouté des statistiques qui indiquent
          le nombre total de tâches, le nombre de tâches à faire
          et le nombre de tâches terminées.
        </p>

        <p>
          Une barre de progression permet également de visualiser
          le pourcentage de tâches terminées.
        </p>

        <p>
          Enfin, nous avons ajouté des actions globales :
          terminer toutes les tâches, remettre toutes les tâches
          à faire, supprimer les tâches terminées et annuler
          la dernière suppression de tâches terminées.
          »
        </p>

      </div>


      <div class="demo-section">

        <h3>
          🖥️ Démonstration du membre 3
        </h3>

        <ol>
          <li>Utiliser la recherche.</li>
          <li>Montrer le filtre « Toutes ».</li>
          <li>Montrer le filtre « À faire ».</li>
          <li>Montrer le filtre « Terminées ».</li>
          <li>Montrer les différentes priorités.</li>
          <li>Montrer les statistiques.</li>
          <li>Montrer la barre de progression.</li>
          <li>Utiliser « Tout terminer ».</li>
          <li>Utiliser « Tout remettre à faire ».</li>
          <li>Montrer la suppression et l'annulation.</li>
        </ol>

      </div>

    </section>


    <!-- =========================
         9. MEMBRE 4
    ========================== -->

    <section class="presentation-card member-presentation">

      <h2>
        👨‍💻 9. Membre 4 — ANDRIAMAMPIHAJA Carmelo
      </h2>

      <div class="member-role">

        <h3>
          🎤 Partie : Vue.js, LocalStorage, GitHub Pages et conclusion
        </h3>

        <p>
          Le quatrième membre explique les concepts techniques
          utilisés dans Vue.js ainsi que la sauvegarde des données
          et le déploiement de l'application.
        </p>

      </div>


      <div class="oral-section">

        <h3>
          🗣️ Texte à présenter à l'oral
        </h3>

        <p>
          « Pour terminer notre présentation, je vais expliquer
          quelques concepts techniques utilisés dans notre projet.
        </p>

        <p>
          Nous avons utilisé ref() pour créer des données réactives.
          Nous avons utilisé computed() pour calculer automatiquement
          les statistiques et la progression.
        </p>

        <p>
          Nous avons utilisé watch() pour surveiller les changements
          des tâches et enregistrer automatiquement les données
          dans le LocalStorage.
        </p>

        <p>
          Le v-model permet de récupérer les informations saisies
          dans les formulaires, tandis que v-for permet d'afficher
          les différentes tâches.
        </p>

        <p>
          Nous avons également utilisé les props et les emits
          pour permettre la communication entre les composants.
        </p>

        <p>
          Le LocalStorage est important car il permet de conserver
          les tâches même lorsque l'utilisateur actualise la page
          ou ferme puis rouvre le navigateur.
        </p>

        <p>
          Pour terminer, nous avons utilisé Git et GitHub afin
          de gérer notre projet et GitHub Pages afin de rendre
          l'application accessible en ligne.
        </p>

        <p>
          Ce projet nous a permis de comprendre les bases de Vue.js 3
          et de développer une application web interactive complète.
          Merci pour votre attention. »
        </p>

      </div>


      <div class="demo-section">

        <h3>
          🖥️ Démonstration du membre 4
        </h3>

        <ol>
          <li>Montrer le bouton Mode sombre / Mode clair.</li>
          <li>Changer le thème de l'application.</li>
          <li>Actualiser la page pour montrer la conservation des tâches.</li>
          <li>Expliquer le fonctionnement du LocalStorage.</li>
          <li>Présenter les concepts Vue.js.</li>
          <li>Montrer le lien GitHub Pages.</li>
          <li>Terminer par la conclusion.</li>
        </ol>

      </div>

    </section>


    <!-- =========================
         10. LOCAL STORAGE
    ========================== -->

    <section class="presentation-card">

      <h2>
        💾 10. Sauvegarde avec LocalStorage
      </h2>

      <p>
        Le LocalStorage est une fonctionnalité du navigateur
        qui permet de stocker des données localement.
      </p>

      <p>
        Dans notre application, les tâches sont automatiquement
        sauvegardées. Ainsi, lorsque l'utilisateur actualise
        la page, ses tâches restent disponibles.
      </p>

      <p>
        Le mode sombre est également sauvegardé afin de conserver
        la préférence de l'utilisateur.
      </p>

      <div class="code-explanation">

        <strong>
          Exemple utilisé dans le projet :
        </strong>

        <pre>
localStorage.setItem(
  'tasks',
  JSON.stringify(newTasks)
)
        </pre>

      </div>

    </section>


    <!-- =========================
         11. GITHUB
    ========================== -->

    <section class="presentation-card github-card">

      <h2>
        🌐 11. Application en ligne
      </h2>

      <p>
        Notre application est disponible en ligne grâce à
        GitHub Pages.
      </p>

      <a
        href="https://manandrazanaeraelien-dev.github.io/l2-gl-2026-groupe-01-todo-app/"
        target="_blank"
        rel="noopener noreferrer"
      >
        🚀 Ouvrir l'application en ligne
      </a>

      <p class="github-description">
        Le déploiement permet de consulter et tester notre
        application directement depuis un navigateur web.
      </p>

    </section>


    <!-- =========================
         12. DEROULEMENT ORAL
    ========================== -->

    <section class="presentation-card">

      <h2>
        🎤 12. Ordre recommandé pour l'exposé
      </h2>

      <div class="oral-order">

        <div>
          <strong>👨‍💻 Membre 1</strong>
          <p>
            Introduction → objectif → technologies → présentation
            générale de l'interface.
          </p>
        </div>

        <div>
          <strong>👩‍💻 Membre 2</strong>
          <p>
            Structure → ajout → modification → suppression →
            terminer une tâche.
          </p>
        </div>

        <div>
          <strong>👨‍💻 Membre 3</strong>
          <p>
            Recherche → filtres → priorités → statistiques →
            progression → actions globales.
          </p>
        </div>

        <div>
          <strong>👨‍💻 Membre 4</strong>
          <p>
            Concepts Vue.js → LocalStorage → mode sombre →
            GitHub → GitHub Pages → conclusion.
          </p>
        </div>

      </div>

    </section>


    <!-- =========================
         13. CONCLUSION
    ========================== -->

    <section class="presentation-card conclusion-card">

      <h2>
        🎓 13. Conclusion
      </h2>

      <p>
        Ce mini-projet nous a permis de mettre en pratique
        les principaux concepts de Vue.js 3.
      </p>

      <p>
        Nous avons appris à créer une application composée de
        plusieurs composants, à gérer des données réactives,
        à utiliser les événements, les props, les emits,
        les directives et les fonctions de Vue.js.
      </p>

      <p>
        Nous avons également appris à sauvegarder les données
        avec LocalStorage, à utiliser Git et GitHub et à déployer
        notre application avec GitHub Pages.
      </p>

      <p>
        Grâce à ce projet, nous avons pu transformer les notions
        théoriques étudiées en classe en une application web
        concrète et interactive.
      </p>

      <h3>
        🙏 Merci pour votre attention !
      </h3>

    </section>

  </div>
</template>