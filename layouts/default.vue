<template>
  <header class="shadow-sm bg-white">
    <nav class="container mx-auto p-4 flex justify-between">
      <NuxtLink to="/" class="font-bold">LOGO</NuxtLink>

      <ul class="flex gap-4">
        <li><NuxtLink to="/">Home</NuxtLink></li>
        <li><NuxtLink to="/about">About</NuxtLink></li>
        <li><NuxtLink to="/products" class="btn">Products</NuxtLink></li>
      </ul>
    </nav>
  </header>

  <section class="mt-5 mx-auto container">
    <slot />
  </section>
</template>

<style scoped>
.router-link-exact-active {
  color: blue;
}
</style>
