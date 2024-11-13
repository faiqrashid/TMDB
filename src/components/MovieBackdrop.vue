<template>
  <div class="relative">
    <div class="aspect-video w-full overflow-hidden">
      <img
        :src="posterUrl"
        :alt="'Movie Backdrop'"
        class="w-full h-full object-cover opacity-70"
      />
      <div class="absolute inset-0 bg-black bg-opacity-30"></div>
    </div>
    <div class="absolute bottom-4 left-4">
      <img
        :src="posterUrl"
        :alt="'Movie Poster'"
        class="w-24 h-36 rounded-lg shadow-lg object-cover"
      />
    </div>
  </div>
</template>

<script setup>
defineProps({
  posterUrl: {
    type: String,
    required: true,
  },
});
</script>
