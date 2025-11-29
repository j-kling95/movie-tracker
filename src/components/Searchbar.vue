<script setup>
import { ref } from 'vue'
const searchTerm = defineModel();

</script>

<template>
  <div class="search-bar-container">
    <input v-model="searchTerm" type="text" placeholder="Search for movies" />
  </div>
  <p>The search term is {{ searchTerm }}</p>
</template>

<style scoped>
.search-bar-container {
  display: flex;
  justify-content: center;
}
input {
  color: rgb(68, 68, 68);
  border: 1px solid white;
  padding: 1rem;
  border-radius: 10px;
  font-size: 1rem;
  width: 90%;
  background-color: white;
}
</style>
