<script setup>
const props = defineProps({
  skills: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <section class="section">
    <div class="section__head">
      <p class="eyebrow">Compétences</p>
      <h2>Des bases solides.</h2>
    </div>
    <div class="skills">
      <article v-for="block in props.skills" :key="block.group" class="skill-card">
        <h3>{{ block.group }}</h3>
        <ul class="skill-list">
          <li v-for="item in block.items" :key="item">{{ item }}</li>
        </ul>
      </article>
    </div>
  </section>
</template>
