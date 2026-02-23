<script setup>
const props = defineProps({
  projects: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <section class="section">
    <div class="section__head">
      <p class="eyebrow">Projets</p>
      <h2>Mes projets personnels et académiques.</h2>
    </div>
    <div class="projects">
      <article v-for="project in props.projects" :key="project.title" class="project-card">
        <div class="project-card__head">
          <h3>{{ project.title }}</h3>
          <a
            v-if="project.link"
            :href="project.link"
            target="_blank"
            rel="noreferrer"
            aria-label="Lien du projet"
            class="icon-link icon-link--sm"
          >
            <svg viewBox="0 0 24 24" aria-hidden="true">
              <path
                d="M12 2.1c-5.5 0-10 4.6-10 10.2 0 4.5 2.9 8.4 6.8 9.7.5.1.7-.2.7-.5v-1.8c-2.8.6-3.4-1.2-3.4-1.2-.5-1.2-1.1-1.5-1.1-1.5-.9-.6.1-.6.1-.6 1 .1 1.6 1 1.6 1 .9 1.5 2.4 1.1 3 .8.1-.7.4-1.1.7-1.4-2.2-.2-4.6-1.1-4.6-5 0-1.1.4-2 1-2.7-.1-.3-.4-1.3.1-2.6 0 0 .8-.3 2.7 1a9.1 9.1 0 0 1 5 0c1.9-1.3 2.7-1 2.7-1 .5 1.3.2 2.3.1 2.6.7.7 1 1.6 1 2.7 0 3.9-2.4 4.8-4.7 5 .4.3.8 1 .8 2v3c0 .3.2.6.7.5 4-1.3 6.9-5.2 6.9-9.7 0-5.6-4.5-10.2-10-10.2z"
              />
            </svg>
          </a>
        </div>
        <div v-if="project.type" class="project-card__tags">
          <span class="chip chip--type">{{ project.type }}</span>
        </div>
        <p class="muted">{{ project.description }}</p>
        <div class="project-card__tags">
          <span v-for="tag in project.stack" :key="tag" class="chip">{{ tag }}</span>
        </div>
      </article>
    </div>
  </section>
</template>
