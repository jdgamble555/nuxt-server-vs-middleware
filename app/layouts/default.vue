<template>
  <div class="flex flex-col gap-4 items-center p-10">
    <slot />
    <nav class="flex gap-4">
      <NuxtLink to="/">Home</NuxtLink>
      <NuxtLink to="/server">Server Component</NuxtLink>
      <NuxtLink to="/fetch">Fetch</NuxtLink>
    </nav>
  </div>
</template>
