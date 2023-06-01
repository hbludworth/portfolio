<template>
  <div class="column testimonial-column">
    <img :src="getImageUrl(imagePath)" class="mt-4 avatar-mini" />
    <p class="is-size-5-tablet mt-4">
      {{ quote }}
    </p>
    <p class="has-text-primary has-text-weight-medium is-size-5-tablet mt-4 title-font">
      {{ name }}
    </p>
    <p class="has-text-primary has-text-weight-normal is-size-6-tablet is-size-7-mobile">
      {{ title }}
    </p>
  </div>
</template>

<script setup lang="ts">
defineProps({
  imagePath: {
    type: String,
    required: true,
  },
  quote: {
    type: String,
    required: true,
  },
  name: {
    type: String,
    required: true,
  },
  title: {
    type: String,
    required: true,
  },
});

const getImageUrl = (name: string) => new URL(`../assets/${name}`, import.meta.url).href;
</script>
