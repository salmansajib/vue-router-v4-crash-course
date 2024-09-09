<script setup>
import cars from "@/data/cars.json";
import { RouterLink } from "vue-router";
</script>

<template>
  <div>
    <h1>Home View</h1>

    <div class="cars">
      <RouterLink :to="`/cars/${car.id}`" v-for="car in cars" :key="car.id">
        {{ car.name }}
      </RouterLink>
    </div>
  </div>
</template>

<style scoped>
h1 {
  margin-top: 2rem;
}

.cars {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 1rem;
  margin-top: 1rem;
}

.cars a {
  background: black;
  padding-inline: 1rem;
  padding-block: 0.5rem;
  border-radius: 0.3rem;
}

.cars a:hover {
  background: rgb(220, 220, 220);
  color: rgb(18, 18, 18);
}
</style>
