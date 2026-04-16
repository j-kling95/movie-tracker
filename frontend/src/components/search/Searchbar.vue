<script setup>
import { ref, watch } from 'vue';

const searchTerm = ref("");

const emit = defineEmits(['notEmpty']);

watch(searchTerm, () => {
    if (searchTerm !== ""){
        emit('notEmpty', searchTerm)
    };

});

</script>

<template>
    <!-- <p>{{ changedResults }}</p> -->
    <div
        class="search-bar-container"
    >
        <input
            @click="console.log('activated')"
            v-model="searchTerm"
            type="text"
            placeholder="Search for movies"
        />
    </div>
    <!-- <p>The search term is {{ searchTerm }}</p> -->
</template>

<style scoped>
.search-bar-container {
    padding: 0.5rem;
    border-radius: 10px;
    box-shadow: 0 0 2px grey;
}

.empty,
.no-results {
    border-radius: 10px;
}

input {
    color: rgb(68, 68, 68);
    border: 4px solid #b2b2b2;
    padding: 1rem;
    border-radius: 10px;
    font-size: 1rem;
    background-color: white;
    width: 100%;
    outline-color: transparent;
}

input:focus {
    border: 4px solid rgb(255, 166, 0);
}

input:focus-visible {
    border: 4px solid rgb(255, 166, 0);
}
</style>
