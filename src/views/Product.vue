<script setup>
import { useRoute } from "vue-router";

const route = useRoute();
</script>

<template>
  <main
    class="w-full h-full flex flex-col justify-center items-center pt-20 space-y-5"
  >
    <p class="text-3xl">Product page</p>
    <p class="text-2xl text-red-500">Product Id: {{ route.params.id }}</p>
  </main>
</template>

<style></style>
