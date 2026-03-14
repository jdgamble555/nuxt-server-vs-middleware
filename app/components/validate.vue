<script lang="ts" setup>
const currentUrl = useRequestURL();

const href = computed(
  () =>
    `https://validator.schema.org/#url=${encodeURIComponent(currentUrl.href)}`,
);
</script>

<template>
  <a class="underline hover:no-underline" :href>Test Schema</a>
</template>
