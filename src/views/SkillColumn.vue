<template>
  <div class="column skill-column">
    <h1 class="title is-size-4 is-spaced title-font">{{ title }}</h1>
    <p>{{ description }}</p>
    <p class="skill-title has-text-primary has-text-weight-medium title-font is-size-5-tablet">
      {{ subtitle1 }}
    </p>
    <p>{{ subtitle1Description }}</p>
    <p class="skill-title has-text-primary has-text-weight-medium title-font is-size-5-tablet">
      {{ subtitle2 }}
    </p>
    <ul>
      <li v-for="item in subtitle2ListItems" :key="item">{{ item }}</li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import type { PropType } from 'vue';

defineProps({
  title: String,
  description: String,
  subtitle1: String,
  subtitle1Description: String,
  subtitle2: String,
  subtitle2ListItems: Array as PropType<string[]>,
});
</script>
