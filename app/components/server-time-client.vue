<script setup lang="ts">
const { data } = await useFetch<{ now: string }>("/api/time");
</script>

<template>
  <div v-if="data">Server time: {{ data.now }}</div>
</template>
