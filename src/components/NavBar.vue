<template>
  <nav
    class="px-6 py-4 bg-[#032541] text-white flex items-center justify-between border-b border-gray-700"
  >
    <div class="flex items-center space-x-8">
      <a href="#" class="text-2xl font-bold text-[#01B4E4]">TMDB</a>
      <div class="flex space-x-6">
        <a
          v-for="item in menuItems"
          :key="item"
          href="#"
          class="hover:text-[#01B4E4]"
          >{{ item }}</a
        >
      </div>
    </div>
    <div class="flex items-center space-x-4">
      <button class="p-2 rounded-full hover:bg-gray-700">
        <PlusIcon class="w-6 h-6" />
      </button>
      <button class="px-3 py-1 border rounded">
        {{ currentLanguage }}
      </button>
      <button class="hover:text-[#01B4E4]">Login</button>
      <button class="hover:text-[#01B4E4]">Join TMDB</button>
      <button class="p-2 rounded-full hover:bg-gray-700">
        <SearchIcon class="w-6 h-6" />
      </button>
    </div>
  </nav>
</template>

<script setup>
import { ref } from "vue";
import { PlusIcon, SearchIcon } from "lucide-vue-next";

const props = defineProps({
  languages: {
    type: Array,
    default: () => ["EN"],
  },
});

const menuItems = ref(["Movies", "TV Shows", "People", "More"]);
const currentLanguage = ref(props.languages[0]);
</script>
