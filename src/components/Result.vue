<script setup>
defineProps({
  title: String,
  genre: String,
  releaseDate: String,
});
</script>

<template>
  <div class="results-container">
    <h4>{{ title }}</h4>
    <p>{{ genre }}</p>
    <p>{{ releaseDate }}</p>
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
    flex-direction: column;
}
</style>
