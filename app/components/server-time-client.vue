<script setup lang="ts">
const modifiedTime = await useAsyncData("time", async () => {
  return new Date().toISOString();
});

useHead({
  meta: [
    {
      property: "article:modified_time",
      content: modifiedTime.data.value,
    },
    {
      name: "last-modified",
      content: modifiedTime.data.value,
    },
  ],
  script: [
    {
      type: "application/ld+json",
      textContent: () =>
        JSON.stringify({
          "@context": "https://schema.org",
          "@type": "WebPage",
          dateModified: modifiedTime.data.value,
        }),
    },
  ],
});
</script>

<template>
  <div v-if="modifiedTime.data">Server time: {{ modifiedTime.data.value }}</div>
  <Validate />
</template>
