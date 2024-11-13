<template>
  <div class="flex-1">
    <h1 class="text-4xl font-bold mb-2">
      {{ movie.Title }}
      <span class="text-gray-400">({{ movie.Year }})</span>
    </h1>
    <div class="flex items-center space-x-2 text-sm mb-4">
      <span class="px-2 py-1 bg-gray-700 rounded">{{ movie.Rated }}</span>
      <span>{{ movie.Released }}</span>
      <span>•</span>
      <span>{{ movie.Runtime }}</span>
    </div>
    <div class="flex items-center space-x-4 mb-6">
      <ActionBar :user-score="movie.Metascore"></ActionBar>
    </div>
    <p class="italic text-gray-400 mb-4">Obviously</p>
    <div class="mb-6">
      <h2 class="text-2xl font-bold mb-2">Overview</h2>
      <p>{{ movie.Plot }}</p>
    </div>
    <div class="grid grid-cols-3 gap-4">
      <div>
        <h3 class="font-bold">{{ movie.Director }}</h3>
        <p class="text-gray-400">Director</p>
      </div>
      <div v-for="(writer, index) in movie.Writer.split(',')" :key="index">
        <h3 class="font-bold">{{ writer.trim() }}</h3>
        <p class="text-gray-400">Writer</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import ActionBar from "./ActionBar.vue";

defineProps({
  movie: {
    type: Object,
    required: true,
  },
});
</script>
