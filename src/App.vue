<script setup>
import SkillsSection from './components/SkillsSection.vue'
import ExperiencesSection from './components/ExperiencesSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'

const profile = {
  name: 'Maxime Piau',
  role: 'Etudiant en BUT informatique',
  location: 'Nantes / Angers / Ancenis (44150)',
  summary:
    'Etudiant en informatique a Nantes.\nCe qui me plaît le plus, c est partir de 0 et voir un projet grandir.',
  links: [
    { label: 'Email', value: 'maxime.piau04@gmail.com' },
    { label: 'GitHub', value: 'https://github.com/Max04git' },
    { label: 'LinkedIn', value: 'https://www.linkedin.com/in/maxime-piau-921169310/' }
  ]
}

const skills = [
  {
    group: 'Langages et Framework',
    items: ['Python', 'HTML', 'CSS', 'Kotlin', 'SpringBoot', 'Golang', 'SQL', 'PHP', 'JavaScript', 
    'TypeScript', 'Angular', 'React', 'Vue.js', 'Symfony']
  },
  {
    group: 'Outils',
    items: ['Gitlab', 'GitHub', 'Visual Studio Code', 'IntelliJ', 'Android Studio', 'Semarchy XDI', 
    'DBeaver', 'Jetpack Compose', 'Google Apps', 'Infor M3']
  },
  {
    group: 'Atouts',
    items: ["Bon esprit d'équipe", 'Polyvalence', 'Logique', 'Curiosité', "Grande capacité d'autonomie",
      'Perfectionniste'
    ]
  }
]

const experiences = [
  {
    title: 'Alternant – Tests fonctionnels & Automatisation ERP M3 - ErpToCloud',
    place: 'Carquefou',
    period: 'Septembre 2025 à août 2025',
    details:
      "Conception, exécution et automatisation de tests fonctionnels. Rédaction de scripts d’automatisation " +
      "(API, Robot Framework, Python). Participation au développement et au paramétrage de workflows métiers" +
      " sur l’ERP Infor M3 (données, API, XPath). Documentation et suivi des évolutions mensuelles."
  },
  {
    title: 'Stage développeur informatique – TERRENA',
    place: 'Ancenis',
    period: 'Avril à juillet 2025',
    details:
      "Refonte de l'interface de données vers Semarchy XDI. Analyse, développement, test et documentation."
  },
]

const projects = [
  {
    title: "Carbur'Ancenis",
    type: "Personnel",
    description:
      "Application Android (Kotlin Jetpack Compose) pour comparer les prix des carburants autour d'une ville choisie. " +
      "Fonctionnalités : recherche de ville (Nominatim), favoris, filtres (type de carburant, rayon, date de mise à jour), " +
      "affichage des stations (prix, adresse, distance, date). Technique : MVVM (ViewModel + StateFlow), Retrofit + OkHttp ",
    stack: ['Kotlin', 'Jetpack Compose', 'Material 3', 'MVVM', 'StateFlow', 'Retrofit', 'OkHttp', 'kotlinx.serialization', 'DataStore'],
    link: 'https://github.com/Max04git/CarburAncenis'
  },
  {
    title: 'Plateforme de réservation Spring Boot (Peoples / Reservation / BFF)',
    type: "Académique",
    description:
      "Architecture microservices avec 3 services : Peoples (CRUD personnes, validation complète, suppression en cascade des réservations), " +
      "Reservation (CRUD réservations avec vérification des personnes, salles et créneaux), et BFF (proxy sécurisé + agrégation). " +
      "Sécurité via Spring Security, ajout du header X-User, stockage users en mémoire ou en base selon configuration.",
    stack: ['Java', 'Spring Boot', 'Spring Security', 'WebClient', 'H2', 'Microservices', 'REST API', 'ControllerAdvice'],
    link: 'https://github.com/Max04git/projet-spring-boot'
  },
  {
    title: 'Analyse de Sentiments - Amazon Reviews',
    type: "Académique",
    description:
      "Projet académique de Data Science sur Amazon Reviews pour prédire la note (1 à 5 étoiles) à partir du texte. " +
      "Pipeline NLP avec spaCy, rééquilibrage des classes, comparaison KNN / Decision Tree / Random Forest, et régression linéaire évaluée par RMSE.",
    stack: ['Python', 'spaCy', 'Scikit-learn', 'imbalanced-learn', 'Pandas', 'NumPy', 'Matplotlib', 'NLP', 'Machine Learning'],
    link: 'https://github.com/lboeglin/amazon-reviews-nlp'
  },
  {
    title: 'Application Android observance médicamenteuse',
    type: "Académique",
    description:
      "Développement d’une application mobile Android en Kotlin Jetpack Compose, intégrant la gestion des prises de " +
      "médicaments (ajout, scan d’ordonnance ...). Projet mené en méthodologie Agile Scrum (Product Owner, réunion Daily...).",
    stack: ['Kotlin', 'Jetpack Compose', 'Postgresql', 'Scrum', 'Kanban', 'CI/CD', 'Figma'],
    link: 'https://github.com/TensioProject'
  },
  {
    title: 'Application Android Movie',
    type: "Académique",
    description:
      "Application Android native basée sur l'API TMDB pour consulter les films et séries du moment, voir les details et rechercher par titre ou genre. " +
      "Projet réalisé en groupe avec plusieurs écrans (accueil, details, recherche, films, séries).",
    stack: ['Android', 'Kotlin', 'TMDB API', 'REST API'],
    link: 'https://github.com/Max04git/AppliTheMovieDB'
  },
  {
    title: 'Site de mini-jeux',
    type: "Personnel",
    description:
      "Mini-jeux JavaScript (allumettes, morpion, mastermind) réalisés pendant l'été 2024 afin de découvrir JavaScript",
    stack: ['JavaScript', 'HTML', 'CSS'],
    link: 'https://github.com/Max04git/jeux'
  },
  {
    title: 'Application Skyjo',
    type: "Académique",
    description:
      "Application cliente Skyjo en Kotlin/JavaFX, développée en architecture MVC à partir d'un serveur de jeu fourni. " +
      "Implémentation des vues JavaFX selon les maquettes et d'un modèle aligné sur les diagrammes de classes et les données serveur.",
    stack: ['Kotlin'],
    link: ''
  },
  {
    title: "Projet d'exploitation de données",
    type: "Académique",
    description:
      'Requêtes base de données sur des bornes de recharge, répartition par départements.',
    stack: ['SQL'],
    link: ''
  },
  {
    title: 'Puissance 4 client-serveur',
    type: "Académique",
    description:
      "Projet de programmation système (R3.05) : jeu Puissance 4 en architecture client-serveur avec protocole complet (connexion, ID joueur, couleurs, tours, résultat, rejouer). " +
      "Travail sur la boucle Update et la machine à états (waiting, colorSelect, play, result) pour contrôler la logique du jeu.",
    stack: ['Golang', 'Programmation système', 'Client-serveur'],
    link: 'https://github.com/Max04git/projet-puissance4'
  },
  {
    title: 'Jeu video 2D (quadtree)',
    type: "Académique",
    description:
      "Projet en Golang : implémentation d'un quadtree avec fonctions update, readFromFile, get et make, plus tests associés. " +
      "Extension du moteur avec terrain aléatoire, sauvegarde, gestion de l'eau non traversable et options activables via config.",
    stack: ['Golang'],
    link: ''
  },
  {
    title: 'Jeu des allumettes',
    type: "Personnel",
    description:
      "Projet solo découverte du langage PHP (2023). Jeu à deux joueurs dans lequel le joueur qui prend la dernière" +
      " allumette a perdu.",
    stack: ['PHP'],
    link: ''
  },
  {
    title: 'Morpion',
    type: "Personnel",
    description:
      'Projet Morpion en Python (2021), une version à 2 joueurs et une version solo contre un bot (aléatoire).',
    stack: ['Python'],
    link: ''
  }
]
</script>

<template>
  <div class="page">
    <aside class="sidebar">
      <div class="sidebar__brand">MP</div>
      <nav class="sidebar__nav">
        <a href="#about">Qui suis-je</a>
        <a href="#skills">Compétences</a>
        <a href="#experience">Expériences</a>
        <a href="#projects">Projets</a>
        <a href="#contact">Contact</a>
      </nav>
      <div class="sidebar__footer">
        <p class="muted">Étudiant BUT info</p>
      </div>
    </aside>

    <div class="page__main">
      <section id="about" class="accueil">
        <div class="accueil__text">
          <p class="eyebrow">Portfolio</p>
          <h1>{{ profile.name }}</h1>
          <p class="accueil__role">{{ profile.role }}</p>
          <p class="accueil__summary">{{ profile.summary }}</p>
          <div class="accueil__meta">
            <span>{{ profile.location }}</span>
          </div>
        </div>
        <div class="accueil__about">
          <p class="eyebrow">Qui suis-je</p>
          <h2>Etudiant curieux et motivé.</h2>
          <p class="lead">
            Je suis Maxime Piau et j'ai 21 ans. Je suis actuellement étudiant en troisième année
            d'informatique à Nantes. J'adore les jeux de logique, les romans et le vélo.
          </p>
          <p class="lead">
            Dans l'informatique, j'apprécie particulièrement l'esprit d'équipe.
            Les projets réalisés m'ont permis d'acquérir de la rigueur.
          </p>
        </div>
      </section>

      <main class="content">
        <section id="skills">
          <SkillsSection :skills="skills" />
        </section>
        <section id="experience">
          <ExperiencesSection :items="experiences" />
        </section>
        <section id="projects">
          <ProjectsSection :projects="projects" />
        </section>
        <section id="contact" class="contact">
          <div class="contact-card">
            <div class="contact-card__head">
              <p class="eyebrow">Contact</p>
              <p class="muted">Disponible pour un CDI ou une alternance.</p>
            </div>
            <div class="contact-card__content">
              <a class="value" :href="`mailto:${profile.links[0].value}`">
                {{ profile.links[0].value }}
              </a>
              <div class="card__icons">
                <a
                  :href="profile.links[1].value"
                  target="_blank"
                  rel="noreferrer"
                  aria-label="GitHub"
                  class="icon-link"
                >
                  <svg viewBox="0 0 24 24" aria-hidden="true">
                    <path
                      d="M12 2.1c-5.5 0-10 4.6-10 10.2 0 4.5 2.9 8.4 6.8 9.7.5.1.7-.2.7-.5v-1.8c-2.8.6-3.4-1.2-3.4-1.2-.5-1.2-1.1-1.5-1.1-1.5-.9-.6.1-.6.1-.6 1 .1 1.6 1 1.6 1 .9 1.5 2.4 1.1 3 .8.1-.7.4-1.1.7-1.4-2.2-.2-4.6-1.1-4.6-5 0-1.1.4-2 1-2.7-.1-.3-.4-1.3.1-2.6 0 0 .8-.3 2.7 1a9.1 9.1 0 0 1 5 0c1.9-1.3 2.7-1 2.7-1 .5 1.3.2 2.3.1 2.6.7.7 1 1.6 1 2.7 0 3.9-2.4 4.8-4.7 5 .4.3.8 1 .8 2v3c0 .3.2.6.7.5 4-1.3 6.9-5.2 6.9-9.7 0-5.6-4.5-10.2-10-10.2z"
                    />
                  </svg>
                </a>
                <a
                  :href="profile.links[2].value"
                  target="_blank"
                  rel="noreferrer"
                  aria-label="LinkedIn"
                  class="icon-link"
                >
                  <svg viewBox="0 0 24 24" aria-hidden="true">
                    <path
                      d="M4.98 3.5a2.5 2.5 0 1 1 0 5 2.5 2.5 0 0 1 0-5zM3 9h4v12H3V9zm7 0h3.8v1.6h.1c.5-1 1.8-2 3.8-2 4.1 0 4.8 2.7 4.8 6.1V21h-4v-5.4c0-1.3 0-3-1.9-3s-2.2 1.4-2.2 2.9V21h-4V9z"
                    />
                  </svg>
                </a>
              </div>
            </div>
          </div>
        </section>
      </main>

      <footer class="footer">
        <p>Maxime PIAU 2026</p>
      </footer>
    </div>
  </div>
</template>
