<template>
  <div class="p-4 space-y-4">
    <h1 class="text-2xl font-bold">
      {{ movie.Title }}
      <span class="text-gray-400">({{ movie.Year }})</span>
    </h1>
    <div class="flex flex-wrap gap-2 text-sm">
      <span class="px-2 py-1 bg-gray-700 rounded">{{ movie.Rated }}</span>
      <span>{{ movie.Released }}</span>
      <span>{{ movie.Runtime }}</span>
    </div>
    <div class="flex items-center space-x-4">
      <!-- <ActionBar :user-score="movie.Metascore"></ActionBar> -->
      <MobileActionBar :user-score="movie.Metascore"></MobileActionBar>
    </div>
    <p class="italic text-gray-400">Obviously</p>
    <div>
      <h2 class="text-xl font-bold mb-2">Overview</h2>
      <p>{{ movie.Plot }}</p>
    </div>
    <div class="grid grid-cols-2 gap-4">
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
import MobileActionBar from "./MobileActionBar.vue";

defineProps({
  movie: {
    type: Object,
    required: true,
  },
});
</script>
