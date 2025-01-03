<template>
  <div class="card experience-card">
    <div class="card-content">
      <div class="media">
        <div class="media-content">
          <b class="is-size-5 has-text-primary">{{ company }}</b>
          <p class="is-size-6">{{ position }}</p>
          <p class="is-size-6">{{ time }}</p>
          <p v-if="positionTwo" class="is-size-6 mt-5">{{ positionTwo }}</p>
          <p v-if="timeTwo" class="is-size-6">{{ timeTwo }}</p>
        </div>
      </div>
    </div>
    <div v-if="hasLine" class="line"></div>
  </div>
</template>

<script setup lang="ts">
defineProps({
  company: {
    type: String,
    required: true,
  },
  position: {
    type: String,
    required: true,
  },
  time: {
    type: String,
    required: true,
  },
  positionTwo: {
    type: String,
    required: false,
  },
  timeTwo: {
    type: String,
    required: false,
  },
  hasLine: {
    type: Boolean,
    required: false,
    default: true,
  },
});
</script>
