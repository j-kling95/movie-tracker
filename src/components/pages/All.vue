<script setup>
import Result from "../Result.vue";
import json from "../../assets/movies.json";

const movies = json;
</script>

<template>
  <h2>Movies</h2>
  <div class="movie-container" v-for="movie in movies">
    <Result
      :title="movie.title"
      :genre="movie.genre"
      :release-date="movie.releaseDate.split('-')[0]"
    />
  </div>
</template>

<style scoped>
.movie-container {
  display: flex;
  gap: 2rem;
  margin: 1rem 0;
  padding: 1rem;
  border: 1px solid transparent;;
  border-radius: 10px;
  background-color: rgb(68, 68, 68);
}

.movie-container:hover {
  background-color: rgb(54, 52, 46);
  border-color: rgb(152, 117, 51);
}

.movie-thumbnail {
    width:80px;
    height: 100px;
    background-color: grey;
    border: 1px solid transparent;
    border-radius: 11px;
    box-shadow: 3px 3px 5px #262626;
}
</style>
