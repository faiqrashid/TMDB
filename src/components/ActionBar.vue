<template>
  <div class="flex items-center space-x-6 mb-8">
    <div class="relative w-16 h-16">
      <div
        class="w-full h-full rounded-full bg-[#081c22] flex items-center justify-center"
      >
        <span class="text-xl font-bold"
          >{{ userScore }}<span class="text-sm">%</span></span
        >
      </div>
      <div
        class="absolute inset-0 rounded-full border-4 border-[#01e401]"
        :style="{
          clipPath: `polygon(0 0, ${userScore}% 0, ${userScore}% 100%, 0 100%)`,
        }"
      ></div>
    </div>

    <button
      v-for="icon in icons"
      :key="icon.name"
      class="p-3 rounded-full hover:bg-gray-700"
    >
      <component :is="icon.component" class="w-6 h-6 fill-current" />
    </button>

    <button class="flex items-center space-x-2 px-4 py-2 text-white rounded-lg">
      <PlayIcon class="w-5 h-5 fill-current" />
      <span>Play Trailer</span>
    </button>
  </div>
</template>

<script setup>
import {
  HeartIcon,
  StarIcon,
  BookmarkIcon,
  ListIcon,
  PlayIcon,
} from "lucide-vue-next";

defineProps({
  userScore: {
    type: Number,
    required: true,
  },
});

const icons = [
  { name: "list", component: ListIcon },
  { name: "heart", component: HeartIcon },
  { name: "bookmark", component: BookmarkIcon },
  { name: "star", component: StarIcon },
];
</script>
