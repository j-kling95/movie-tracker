<script setup>
import { computed, watch } from "vue";
import json from "../../assets/movies.json";
import Result from "../Result.vue";

let movies = json;

const searchTerm = defineProps(["searchTerm"]);

const emit = defineEmits(['changedResults']);

const activeMovies = computed(() => {
  let updatedMovies = [];
  for (let object of movies) {
    delete object.rating;
    console.log(object);
    for (let key of Object.keys(object)) {

      let value = String(object[key]).toLowerCase();
      let term = searchTerm.searchTerm.toLowerCase();
      if (value.search(term) !== -1 && term != "") { 
        updatedMovies.push(object);
        console.log("object found");
        break;
      }
    }
  }
  console.log(updatedMovies.length);
  return updatedMovies;
});

function emitResults (){
    emit('changedResults');
    console.log("emit performed");
};

watch(() => activeMovies.value.length, (newValue, oldValue) => {
    console.log("old value: " + oldValue);
    console.log("new value: " + newValue);

    if (newValue === 0 && oldValue !== 0) {
        emitResults();
    } else if (oldValue === 0 && newValue !== 0) {
        emitResults();
    };

});

</script>

<template>
    <!-- <p>{{ activeMovies.length }}</p> -->
  <div :class="{ empty: activeMovies.length === 0 }" class="search-results">
    <div class="search-result-container" v-for="movie in activeMovies">
      <Result
        :title="movie.title"
        :genre="movie.genre"
        :release-date="movie.releaseDate.split('-')[0]"
      />
    </div>
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

.empty {
  padding: 0;
}
</style>
