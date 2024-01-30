<template>
  <div>
    <h2>Product details for {{ id }}</h2>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. At id cumque quas
      a aliquam voluptatum, perspiciatis modi dolores tempora? Quo tempora nobis
      ex dolore dicta harum soluta est modi laudantium.
    </p>
  </div>
</template>

<script setup>
const { id } = useRoute().params;

definePageMeta({
  layout: "products",
});
</script>

<style scoped></style>
