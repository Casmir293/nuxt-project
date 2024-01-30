<template>
  <div>
    <p>{{ product.title }}</p>
    <p>{{ product.price }}</p>
    <p>{{ product.id }}</p>
  </div>
</template>

<script setup>
import { baseURL } from "../../services/baseURL";
const { id } = useRoute().params;
const productID = baseURL + `/products/${id}`;

definePageMeta({
  layout: "products",
});

// Fetch Products
const { data: product } = await useFetch(productID, { key: id });
</script>

<style scoped></style>
