<script setup>
import { ref } from 'vue'
const searchTerm = defineModel();

</script>

<template>
  <div class="search-bar-container">
    <input v-model="searchTerm" type="text" placeholder="Search for movies" />
  </div>
  <!-- <p>The search term is {{ searchTerm }}</p> -->
</template>

<style scoped>
.search-bar-container {
  display: flex;
  justify-content: center;
  padding: 1rem 1rem 0.5rem;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
  background-color: white;
  width: 90%;
  margin: 0 auto;
}
input {
  color: rgb(68, 68, 68);
  border: 2px solid #b2b2b2;
  padding: 1rem;
  border-radius: 10px;
  font-size: 1rem;
  background-color: white;
  width: 100%;
}

input:focus {
    border-color: rgb(152, 117, 51);
}

input:focus-visible{
    border-color:transparent;
}
</style>
