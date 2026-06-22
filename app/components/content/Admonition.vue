<script setup lang="ts">
withDefaults(defineProps<{
  title?: string
  type?: 'info' | 'success' | 'warning' | 'danger' | 'error'
}>(), {
  type: 'info',
})

const labels: Record<string, string> = {
  info: 'ℹ Info',
  success: '✓ Success',
  warning: '⚠ Warning',
  danger: '✕ Danger',
  error: '✕ Error',
}
</script>

<template>
  <aside :class="['admonition', `admonition--${type}`]">
    <p class="admonition__title">
      {{ title ?? labels[type] }}
    </p>
    <div class="admonition__body">
      <slot mdc-unwrap="p" />
    </div>
  </aside>
</template>

<style scoped>
.admonition {
  margin: 1.5rem 0;
  border-left: 4px solid;
  border-radius: 4px;
  padding: 0.75rem 1rem;
}
.admonition--info    { border-color: #3b82f6; background: #eff6ff; }
.admonition--success { border-color: #22c55e; background: #f0fdf4; }
.admonition--warning { border-color: #eab308; background: #fefce8; }
.admonition--danger,
.admonition--error   { border-color: #ef4444; background: #fef2f2; }
.admonition__title {
  font-weight: 700;
  margin: 0 0 0.5rem 0;
}
.admonition--info    .admonition__title { color: #3b82f6; }
.admonition--success .admonition__title { color: #22c55e; }
.admonition--warning .admonition__title { color: #ca8a04; }
.admonition--danger  .admonition__title,
.admonition--error   .admonition__title { color: #ef4444; }
.admonition__body {
  color: #555;
}
</style>
