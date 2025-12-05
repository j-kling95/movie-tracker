<script setup>
//import HelloWorld from './components/HelloWorld.vue'
import Layout from "./components/layouts/Layout.vue";
import All from "./components/pages/All.vue";
import Home from "./components/pages/Home.vue";
import Watched from "./components/pages/Watched.vue";
import Watchlist from "./components/pages/Watchlist.vue";

const activePage = 1;
</script>

<template>
    <Layout>
        <Home v-if="activePage == 0" />
        <All v-if="activePage == 1" />
        <Watched v-if="activePage == 2" />
        <Watchlist v-if="activePage == 3" />
    </Layout>
</template>
<style scoped>

</style>
