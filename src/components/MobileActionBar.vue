<template>
  <div class="flex items-center space-x-6 mb-8">
    <!-- User Score Section -->
    <div class="relative w-16 h-16">
      <div
        class="w-full h-full rounded-full bg-[#081c22] flex items-center justify-center"
      >
        <span class="text-xl font-bold">
          {{ userScore }}<span class="text-sm">%</span>
        </span>
      </div>
      <div
        class="absolute inset-0 rounded-full border-4 border-[#01e401]"
        :style="{
          clipPath: `polygon(0 0, ${userScore}% 0, ${userScore}% 100%, 0 100%)`,
        }"
      ></div>
    </div>
    <div>
      <p class="font-bold">User Score</p>
    </div>
    <div class="border-r-2 h-12 border-gray-500 mx-4"></div>

    <!-- Play Trailer Button -->
    <button
      class="flex items-center space-x-2 px-4 py-2 text-white rounded-lg hover:bg-[#0099c9]"
    >
      <PlayIcon class="w-5 h-5" />
      <span>Play Trailer</span>
    </button>
  </div>
</template>

<script setup>
import { PlayIcon } from "lucide-vue-next";

defineProps({
  userScore: {
    type: Number,
    required: true,
  },
});
</script>
