<template>
  <div class="flex items-center justify-center w-full bg-white">
    <div class="bg-white text-black border-gray-700 w-full max-w-4xl">
      <div class="container mx-auto px-4 py-2">
        <div class="flex justify-center space-x-8">
          <a
            v-for="tab in tabs"
            :key="tab"
            href="#"
            @click.prevent="setActiveTab(tab)"
            class="flex items-center px-4 py-2 whitespace-nowrap"
            :class="[
              'pb-2',
              'hover:text-gray-400',
              activeTab === tab
                ? 'border-b-4 border-[#01B4E4] text-gray-900'
                : 'text-black',
            ]"
          >
            {{ tab }}
            <ChevronDownIcon class="ml-2 w-4 h-4" />
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { ChevronDownIcon } from "lucide-vue-next";

const activeTab = ref("Overview");

const tabs = ["Overview", "Media", "Fandom", "Share"];

function setActiveTab(tab) {
  activeTab.value = tab;
}
</script>
