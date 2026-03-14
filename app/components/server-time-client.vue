<script setup lang="ts">
const { data } = await useFetch<{ now: string }>("/api/time");

const modifiedTime = computed(() => data.value?.now ?? "");

useHead({
  meta: [
    {
      property: "article:modified_time",
      content: modifiedTime,
    },
    {
      name: "last-modified",
      content: modifiedTime,
    },
  ],
  script: [
    {
      type: "application/ld+json",
      textContent: () =>
        JSON.stringify({
          "@context": "https://schema.org",
          "@type": "WebPage",
          dateModified: modifiedTime.value,
        }),
    },
  ],
});
</script>

<template>
  <div v-if="data">Server time: {{ data.now }}</div>
  <Validate />
</template>
