<script setup lang="ts">
import MovieCard from '@/components/MovieCard.vue'
import { useStoreDVDs } from '@/stores/storeDVDs'
import isLoading from '@/components/isLoading.vue'

const items = useStoreDVDs()
</script>

<template>
  <template v-if="!items.DVDsLoaded">
    <isLoading />
  </template>
  <template v-else>
    <div class="mb-3">
      Currently there are <span class="font-bold">{{ items.DVDs.length }}</span> titles in the
      database.
    </div>
    <div class="grid sm:grid-cols-2 xl:grid-cols-3 gap-6 mb-6">
      <MovieCard
        v-for="item in items.DVDs"
        :key="item.id"
        :id="item.id"
        :name="item.name"
        :rating="item.rating"
      />
    </div>
    <div v-if="!items.DVDs.length">
      <h1>No DVDs found...</h1>
    </div>
  </template>
</template>
