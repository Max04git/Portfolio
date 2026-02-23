<script setup>
const props = defineProps({
  profile: {
    type: Object,
    required: true
  }
})
</script>

<template>
  <section class="section">
    <div class="section__head">
      <p class="eyebrow">À propos</p>
      <h2>Une approche simple, utile, robuste.</h2>
    </div>
    <div class="section__body grid-2">
      <p class="lead">
        {{ props.profile.summary }}
      </p>
      <div class="info-card">
        <p class="info-card__title">Ce que je cherche</p>
        <p class="info-card__text">
          Collaborer avec des équipes qui valorisent la qualité, la vitesse
          d'iteration et l'impact.
        </p>
        <div class="info-card__chips">
          <span class="chip">UX claire</span>
          <span class="chip">Code propre</span>
          <span class="chip">Performance</span>
        </div>
      </div>
    </div>
  </section>
</template>
