<script setup>
import { ref } from "vue";
import Searchbar from "./Searchbar.vue";
import Searchresults from "./Searchresults.vue";

const searchTerm = ref("");
const results = ref(false);

</script>

<template>
  <Searchbar  :changed-results="results" v-model="searchTerm"/>
  <Searchresults 
  @changed-results="results = !results"
  :search-term="searchTerm"
  />
</template>

<style computed></style>