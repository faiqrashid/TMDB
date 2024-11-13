<template>
  <header class="bg-[#032541] text-white p-4 flex items-center justify-between">
    <button class="p-2 rounded-full hover:bg-gray-700">
      <Menu class="w-6 h-6" />
    </button>

    <div class="flex-grow text-2xl font-bold text-[#01B4E4] text-center">
      TMDB
    </div>

    <div class="flex space-x-4">
      <button class="p-2 rounded-full hover:bg-gray-700">
        <User2Icon class="w-6 h-6" />
      </button>
      <button class="p-2 rounded-full hover:bg-gray-700">
        <SearchIcon class="w-6 h-6" />
      </button>
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";
import { Menu, SearchIcon, User2Icon } from "lucide-vue-next";
</script>
