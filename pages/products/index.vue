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

// Layout Template
definePageMeta({
  layout: "products",
});

// Fetch Products
const { data: products } = await useFetch(baseURL + "/products");

// This useHead is used to give title and metatags on a specific page
useHead({
  title: "Solo Store | Products",
  meta: [{ name: "description", content: "Solo Store Products" }],
});
</script>

<style lang="scss" scoped></style>
