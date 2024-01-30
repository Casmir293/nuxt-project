<template>
  <div>
    <ProductDetails :product="product" />
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

if (!product.value) {
  throw createError({ statusCode: 404, statusMessage: "Product not found" });
}
</script>

<style scoped></style>
