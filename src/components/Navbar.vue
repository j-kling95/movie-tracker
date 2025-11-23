<script setup>
import { ref } from 'vue'

const pages = [
    { name: 'All' },
    { name: 'Watched' },
    { name: 'TBW' }
]

</script>

<template>
    <ul>
        <div class="home-container">
            <li class="logo"><img src="../assets/platypus-logo.png" alt="Ernie-Logo"></li>
        </div>
        <div class="link-container">

        <li class="logo-links" v-for="(page, index) in pages">{{ page.name }}</li>
        </div>
    </ul>
</template>

<style scoped>
ul {
    display: flex;
    list-style: none;
    justify-content: space-between;
    align-items: center;
    padding: 0;
}

.link-container {
    display: flex;
    gap: 2em;
}
.logo {
    width: 100px;
    height: 100px;
    background-color: rgb(54, 52, 46);
    border-radius: 50%;
    border: 2px solid rgb(152, 117, 51);
}

img {
    object-fit: fill;
    overflow: hidden;
    width: 100%;
    height: 100%;
}


</style>