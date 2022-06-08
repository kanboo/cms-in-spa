<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header class="border-b-2 border-black py-5">
    <div class="wrapper">
      <nav class="text-xl text-center space-x-5">
        <RouterLink to="/">Home</RouterLink>
        <span>/</span>
        <RouterLink to="/about">About</RouterLink>
        <span>/</span>
        <RouterLink to="/event-page">Event Page</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style>
@tailwind base;
@tailwind components;
@tailwind utilities;
</style>
