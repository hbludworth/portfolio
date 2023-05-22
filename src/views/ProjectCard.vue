<template>
  <div class="card">
    <div class="card-header">
      <h1 class="card-header-title">{{ title }}</h1>
    </div>
    <div class="card-image">
      <figure class="image is-16x9">
        <img :src="getImageUrl(imagePath)" :alt="title" />
      </figure>
    </div>
    <div class="card-content">
      <div class="content is-size-6">
        {{ description }}
      </div>
    </div>
    <footer class="card-footer">
      <span v-if="viewLink" class="icon-text card-footer-item">
        <a :href="viewLink" target="_blank">
          <span>View</span>
          <span class="icon">
            <i class="mdi mdi-open-in-new"></i>
          </span>
        </a>
      </span>
      <span v-if="githubLink" class="icon-text card-footer-item">
        <a :href="githubLink" target="_blank">
          <span>GitHub</span>
          <span class="icon">
            <i class="mdi mdi-open-in-new"></i>
          </span>
        </a>
      </span>
    </footer>
  </div>
</template>

<script setup lang="ts">
defineProps({
  title: {
    type: String,
    required: true,
  },
  imagePath: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
  viewLink: String,
  githubLink: String,
});

const getImageUrl = (name: string) => new URL(`../assets/${name}`, import.meta.url).href;
</script>
