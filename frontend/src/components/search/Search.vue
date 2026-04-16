<script setup>
import { ref } from "vue";
import Searchbar from "./Searchbar.vue";
import Searchresults from "./Searchresults.vue";

const searchTerm = ref("");

const emit = defineEmits(["notEmpty"])

function propagateSearchResult(inputText) {
    searchTerm.value = inputText;
    emit("notEmpty", searchTerm.value);
};

</script>

<template>
    <div class="search-container">
        <Searchbar @not-empty="propagateSearchResult" v-model="searchTerm"/> 
        <!-- 
      <Searchresults
      @changed-results="results = !results"
      :search-term="searchTerm"
      /> -->
    </div>
</template>

<style computed>
.search-container {
    padding-bottom: 0.5rem;
}
</style>
