<template>
  <nav class="bg-white text-black overflow-x-auto">
    <div class="flex p-2 justify-between">
      <a
        href="#"
        v-for="tab in tabs"
        :key="tab"
        class="flex items-center px-4 py-2 whitespace-nowrap"
        :class="{
          'border-b-2 border-[#01B4E4]': activeTab === tab,
          'text-[#01B4E4]': activeTab === tab,
          'text-gray-700': activeTab !== tab,
        }"
        @click.prevent="setActiveTab(tab)"
      >
        {{ tab }}
        <ChevronDownIcon class="ml-2 w-4 h-4" />
      </a>
    </div>
  </nav>
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
