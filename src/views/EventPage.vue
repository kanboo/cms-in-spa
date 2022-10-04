<script setup>
import { onMounted, onUnmounted } from "vue";
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

const offNavigateBehindTo =
  window.HANDSUP_CMS.onNavigateBehindTo(triggerRedirect);

onMounted(() => {
  window.HANDSUP_CMS.build();
});

onUnmounted(() => {
  offNavigateBehindTo?.();
});
</script>

<template>
  <div id="hu_app"></div>
</template>
