<template>
  <nav class="navbar is-transparent" role="navigation" aria-label="main navigation">
    <div class="container">
      <div class="navbar-brand">
        <RouterLink class="navbar-item" to="/"> Home </RouterLink>

        <a
          role="button"
          class="navbar-burger"
          aria-label="menu"
          aria-expanded="false"
          data-target="navbarMenu"
        >
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>

      <div id="navbarMenu" class="navbar-menu">
        <div class="navbar-end">
          <RouterLink class="navbar-item" to="/projects"> Projects </RouterLink>

          <RouterLink class="navbar-item" to="/writing"> Writing </RouterLink>

          <RouterLink class="navbar-item" to="/resume"> Resume </RouterLink>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts"></script>
