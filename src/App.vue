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
  <div>
    <Layout>
      <Home v-if="activePage == 0" />
      <All v-if="activePage == 1" />
      <Watched v-if="activePage == 2" />
      <Watchlist v-if="activePage == 3" />
    </Layout>
  </div>
</template>
<style scoped>
h1 {
  color: rgb(152, 117, 51);
}

div {
  background-color: rgb(47, 47, 47);
  border: 1px solid transparent;
  border-radius: 10px;
  box-shadow: 0 0 2px #656565;
}
</style>
