<template>
  <div class="column testimonial-column">
    <img :src="imagePath" class="mt-4 avatar-mini" />
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
  imagePath: String,
  quote: String,
  name: String,
  title: String,
});
</script>
