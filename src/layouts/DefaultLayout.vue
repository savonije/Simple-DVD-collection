<script setup lang="ts">
import PageHeader from '@/components/PageHeader.vue'
import PageFooter from '@/components/PageFooter.vue'
</script>

<template>
  <PageHeader />
  <main class="container flex-grow">
    <slot />
  </main>
  <PageFooter />
</template>
