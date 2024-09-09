<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <div class="nav-links">
    <RouterLink active-class="active" to="/">Home</RouterLink>
    <RouterLink active-class="active" to="/about">About</RouterLink>
  </div>
</template>

<style scoped>
.nav-links {
  display: flex;
  gap: 1rem;
  align-items: center;
}

.active {
  background: green;
  color: white;
  padding-inline: 1rem;
  padding-block: 0.5rem;
}
</style>
