<template>
  <div>
    <div class="grid grid-cols-4 gap-5">
      <div v-for="p in products">
        <product-card :product="p" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { baseURL } from "../../services/baseURL";

definePageMeta({
  layout: "products",
});

// Fetch Products
const { data: products } = await useFetch(baseURL + "/products");
</script>

<style lang="scss" scoped></style>
