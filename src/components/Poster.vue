<template>
  <div class="w-64 flex-shrink-0">
    <img
      :src="posterUrl"
      :alt="'Movie Poster'"
      class="w-full rounded-lg shadow-lg"
    />
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
