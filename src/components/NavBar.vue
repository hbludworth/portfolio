<template>
  <nav class="navbar is-transparent" role="navigation" aria-label="main navigation">
    <div class="container">
      <div class="navbar-brand">
        <RouterLink class="navbar-item" to="/">
          <img src="@/assets/logo.png" class="logo mb-1" />
        </RouterLink>

        <a
          role="button"
          class="navbar-burger"
          :class="{ 'is-active': menuIsActive }"
          aria-label="menu"
          aria-expanded="false"
          @click="menuIsActive = !menuIsActive"
        >
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>

      <div class="navbar-menu" :class="{ 'is-active': menuIsActive }">
        <div class="navbar-end">
          <a class="navbar-item" href="#about">About</a>
          <a class="navbar-item" href="#projects">Projects</a>
          <a class="navbar-item" href="#experience">Experience</a>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const menuIsActive = ref(false);
</script>
