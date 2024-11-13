<template>
  <nav
    class="fixed bottom-0 h-40 left-0 right-0 bg-[#032541] border-t border-gray-700 opacity-95"
  >
    <div class="flex justify-center items-center p-4">
      <img src="#" alt="Navigation Image" class="w-12 h-8 mr-4" />
    </div>

    <div class="flex justify-around items-center h-full mb-4 p-4">
      <button v-for="icon in icons" :key="icon" class="text-white">
        <component :is="icon" class="w-8 h-6 fill-current" />
      </button>
    </div>
  </nav>
</template>

<script setup>
import { List, Heart, Bookmark, Star } from "lucide-vue-next";

const icons = [List, Heart, Bookmark, Star];
</script>
