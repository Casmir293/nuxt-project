<template>
  <div>
    <!-- This head tag is another way that is used to give title and metatags on a specific page -->
    <Head>
      <Title>Solo Store | {{ product.title }}</Title>
      <Meta name="description" :content="product.description" />
    </Head>

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
