<script setup>
import { computed } from "vue";
import json from "../assets/movies.json";
import Result from "./Result.vue";

const movies = json;

const searchTerm = defineProps(['searchTerm'])

const activeMovies = computed(() => {
  let updatedMovies = [];
  for (let object of movies) {
    for (let key of Object.keys(object)) {
      let value = String(object[key]);
      let term = searchTerm.searchTerm;
      if (value.search(searchTerm.searchTerm) !== -1 && searchTerm.searchTerm != "") {
        updatedMovies.push(object);
      }
    }
  }
  return updatedMovies;
});

</script>

<template>
  <div class="search-results">
    <div class="search-result-container" v-for="movie in activeMovies">
        <Result 
        :title="movie.title"
        :genre="movie.genre"
        :release-date="movie.releaseDate.split('-')[0]"
        />
    </div>
    <p v-if="activeMovies.length === 0">No movie found</p>
  </div>
</template>

<style computed>
.search-results {
  background-color: white;
  color: rgb(68, 68, 68);
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 1rem;
  width: 90%;
  margin: 0 auto;
  border-bottom-left-radius: 10px;
  border-bottom-right-radius: 10px;
}

.search-result-container {
  border: 1px solid #b2b2b2;
  padding: 0.5rem 1rem;
  border-radius: 10px;
}

.search-result-container:hover {
    background-color: #dfdfdf;
}
</style>
