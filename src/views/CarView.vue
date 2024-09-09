<script setup>
import { useRoute, useRouter, RouterView } from "vue-router";
import cars from "@/data/cars.json";

const route = useRoute();
const router = useRouter();

const carId = parseInt(route.params.id);

const car = cars.find((c) => c.id === carId);
</script>

<template>
  <div v-if="car" class="card">
    <h1>{{ car.name }}</h1>
    <p>
      Price: <span>{{ car.price }}$</span>
    </p>
    <p>
      Production Year: <span>{{ car.year }}</span>
    </p>
    <button @click="router.push(`/cars/${carId}/contact`)">Contact Info</button>
    <RouterView />
  </div>

  <div v-else>
    <h1>Car not found!</h1>
  </div>
</template>

<style scoped>
.card {
  margin-top: 2rem;
  background: rgb(14, 14, 14);
  width: max-content;
  padding: 2rem;
  color: rgb(0, 163, 0);
  border-radius: 0.5rem;
}

.card p {
  font-weight: 500;
  font-size: 1.2rem;
}

.card p span {
  color: rgb(129, 129, 253);
}
</style>
