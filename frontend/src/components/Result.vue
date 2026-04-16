<script setup>
defineProps({
  title: String,
  genre: String,
  releaseDate: String,
  thumbnailLink: String,
});
</script>

<template>
  <div class="results-container">
    <img class="movie-thumbnail" :src="thumbnailLink" alt="">
    <div class="data">
        <h4>{{ title }}</h4>
        <p>{{ genre }}</p>
        <p>{{ releaseDate }}</p>
    </div>
  </div>
</template>

<style computed>
h4 {
  padding: 0;
  padding-bottom: 0.5rem;
  margin: 0;
  font-size: large;
  font-weight: bold;
}

p {
  padding: 0;
  margin: 0;
}

.results-container {
    display:flex;
    gap: 2rem;
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
