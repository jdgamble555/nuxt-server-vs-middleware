<script setup lang="ts">
const modifiedTime = new Date().toISOString();

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
          dateModified: modifiedTime,
        }),
    },
  ],
});
</script>

<template>
  <div>Server time: {{ modifiedTime }}</div>
</template>
