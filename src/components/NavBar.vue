<template>
  <nav class="navbar is-transparent" role="navigation" aria-label="main navigation">
    <div class="container">
      <div class="navbar-brand">
        <RouterLink class="navbar-item" to="/"> Home </RouterLink>

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
          <RouterLink class="navbar-item" to="/projects" @click="menuIsActive = !menuIsActive">
            Projects
          </RouterLink>

          <RouterLink class="navbar-item" to="/experience" @click="menuIsActive = !menuIsActive">
            Experience
          </RouterLink>

          <div class="nav-bar-item is-flex is-align-items-center ml-2">
            <a
              class="button is-primary is-outlined is-rounded"
              href="mailto:dev@harrisonbludworth.com"
              >Message Me</a
            >
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const menuIsActive = ref(false);
</script>
