<template>
  <div class="grid grid-cols-4 gap-5">
    <div v-for="p in products">
      <NuxtLink :to="`/products/${p.id}`">{{ p.title }}</NuxtLink>
    </div>
  </div>
</template>

<script setup>
import { baseURL } from "../../services/baseURL";

definePageMeta({
  layout: "products",
});

// Fetch Products
const { data: products } = await useFetch(baseURL);
</script>

<style lang="scss" scoped></style>
