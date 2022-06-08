<script setup>
import { onMounted, onBeforeMount } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();

const triggerRedirect = (data) => {
  const { url } = data;
  const parseUrl = new URL(url);

  router.push({
    name: "Product",
    params: { id: parseUrl.searchParams.get("i_code") },
  });
};

onMounted(() => {
  window.HANDSUP_CMS.build();

  window.HANDSUP_CMS.on(
    window.HANDSUP_CMS.EVENT.NAVIGATE_BEHIND_TO,
    triggerRedirect
  );
});

onBeforeMount(() => {
  window.HANDSUP_CMS.off(
    window.HANDSUP_CMS.EVENT.NAVIGATE_BEHIND_TO,
    triggerRedirect
  );
});
</script>

<template>
  <div id="hu_app"></div>
</template>
