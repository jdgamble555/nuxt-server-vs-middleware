<template>
  <div class="flex flex-col items-center gap-4 p-10">
    <slot />
    <nav class="flex gap-4">
      <NuxtLink to="/" active-class="font-bold" exact-active-class="font-bold">
        Home
      </NuxtLink>
      <NuxtLink
        to="/server"
        active-class="font-bold"
        exact-active-class="font-bold"
      >
        Server Component
      </NuxtLink>
      <NuxtLink
        to="/fetch"
        active-class="font-bold"
        exact-active-class="font-bold"
      >
        Fetch
      </NuxtLink>
    </nav>
  </div>
</template>
