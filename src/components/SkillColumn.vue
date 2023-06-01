<template>
  <div class="column skill-column py-6">
    <div class="box icon-circle mx-auto has-background-info">
      <p class="mt-1">
        <span class="icon">
          <span :class="`mdi mdi-36px has-text-white ${icon}`" />
        </span>
      </p>
    </div>
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
  icon: {
    type: String,
    required: true,
  },
  title: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
  subtitle1: {
    type: String,
    required: true,
  },
  subtitle1Description: {
    type: String,
    required: true,
  },
  subtitle2: {
    type: String,
    required: true,
  },
  subtitle2ListItems: { type: Array as PropType<string[]>, required: true },
});
</script>
