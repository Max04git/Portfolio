<script setup>
const props = defineProps({
  items: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <section class="section">
    <div class="section__head">
      <p class="eyebrow">Expériences</p>
      <h2>Mon parcours.</h2>
    </div>
    <div class="timeline">
      <article v-for="item in props.items" :key="item.title" class="timeline__item">
        <div class="timeline__badge"></div>
        <div class="timeline__content">
          <div class="timeline__top">
            <h3>
              {{ item.title }} -
              <a v-if="item.companyUrl" :href="item.companyUrl" target="_blank" rel="noreferrer">
                {{ item.company }}
              </a>
              <span v-else>{{ item.company }}</span>
            </h3>
            <span class="muted">{{ item.period }}</span>
          </div>
          <p class="muted">{{ item.place }}</p>
          <p>{{ item.details }}</p>
        </div>
      </article>
    </div>
  </section>
</template>
