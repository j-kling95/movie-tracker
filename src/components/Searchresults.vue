<script setup>
import json from "../assets/movies.json";

const movies = json;

const searchTerm = "Romance";

function findMovies(entry, term) {
  const dataKeys = Object.keys(entry);

  for (let dataKey in dataKeys) {
    let keyValue = entry[dataKeys[dataKey]];

    if (keyValue == term) {
      console.log("True");
      return true;
    } else {
      console.log(`Search Term not found`);
    }
  }
  return false;
}
</script>

<template>
  <div class="search-results">
  <div class="search-result-container" v-for="movie in movies" v-if="findMovies(movie, searchTerm)">
    <div class="search-result" v-if="findMovies(movie, searchTerm)">
      <h4>{{ movie.title }}</h4>
      <p>{{ movie.genre }}</p>
      <p>{{ movie.releaseDate }}</p>
    </div>
  </div>
</div>
</template>

<style computed>

.search-results {
    background-color: white;
    color: black;
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

.search-result-container {
border: 1px solid black;
}


</style>
