<script setup lang="ts">
const { data: pages } = await useAsyncData('content', () =>
  queryCollection('content').all()
)
</script>

<template>
  <div>
    <NuxtRouteAnnouncer />
    <main style="max-width: 720px; margin: 2rem auto; font-family: sans-serif;">
      <ContentRenderer
        v-for="page in pages"
        :key="page.path"
        :value="page"
      />
    </main>
  </div>
</template>
