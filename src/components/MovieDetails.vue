<template>
  <div class="min-h-screen bg-[#032541] text-white">
    <div v-if="loading" class="flex justify-center items-center h-screen">
      <div
        class="animate-spin rounded-full h-32 w-32 border-t-2 border-b-2 border-[#01B4E4]"
      ></div>
    </div>
    <div v-else-if="error" class="flex justify-center items-center h-screen">
      <p class="text-red-500 text-xl">{{ error }}</p>
    </div>
    <template v-else>
      <div class="hidden md:block">
        <NavBar />
        <SubNavBar></SubNavBar>
        <main class="mx-auto py-8 relative w-full h-full">
          <div
            class="absolute inset-0 bg-cover bg-center opacity-10"
            :style="{ backgroundImage: `url(${movie.Poster})` }"
          ></div>

          <div class="relative z-10 container mx-auto flex gap-8">
            <Poster :posterUrl="movie.Poster" />

            <MovieInfo :movie="movie" />
          </div>
        </main>
      </div>

      <!-- Mobile View -->
      <div class="md:hidden">
        <MobileHeader></MobileHeader>
        <MobileSubNav />
        <main>
          <MovieBackDrop :posterUrl="movie.Poster" />
          <MobileMovieInfo :movie="movie" />
        </main>
        <MobileBottomNav />
      </div>
    </template>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import NavBar from "./NavBar.vue";
import MovieInfo from "./MovieInfo.vue";
import MobileSubNav from "./MobileSubNav.vue";
import MobileMovieInfo from "./MobileMovieInfo.vue";
import MobileBottomNav from "./MobileBottomNav.vue";
import SubNavBar from "./SubNavBar.vue";
import MobileHeader from "./MobileHeader.vue";
import Poster from "./Poster.vue";
import MovieBackDrop from "./MovieBackdrop.vue";

const movie = ref(null);
const loading = ref(true);
const error = ref(null);

const fetchMovieData = async () => {
  try {
    const response = await fetch(
      "http://www.omdbapi.com/?i=tt3896198&apikey=d2132124"
    );
    const data = await response.json();
    if (data.Response === "True") {
      movie.value = data;
    } else {
      throw new Error(data.Error);
    }
  } catch (err) {
    console.error("Error fetching movie data:", err);
    error.value = "Failed to fetch movie data";
  } finally {
    loading.value = false;
  }
};

onMounted(() => {
  fetchMovieData();
});
</script>
