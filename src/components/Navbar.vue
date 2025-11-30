<script setup>
import { ref  } from "vue";
import Search from "./search/Search.vue";

const pages = [{ name: "All" }, { name: "Watched" }, { name: "Watchlist" }];

const activePage = ref(0);


</script>

<template>
  <div id="navbar">
    <ul>
      <div class="home-container" :class="{activelogo: activePage == 0}">
        <li class="logo">
          <a href="#" @click="activePage = 0"
            ><img src="../assets/platypus-logo.png" alt="Ernie-Logo"
          /></a>
        </li>
      </div>
      <div class="link-container">
        <li class="logo-links" v-for="(page, index) in pages">
          <a
            href="#"
            class="pages"
            @click="activePage = index + 1"
            :class="{ active: activePage == index + 1 }"
            >{{ page.name }}</a
          >
        </li>
      </div>
    </ul>
  </div>
  <Search />
</template>

<style scoped>
#navbar {
  padding-bottom: 0;
  border-bottom: 1px solid #656565;
  margin-bottom: 1rem;
}
ul {
  display: flex;
  list-style: none;
  justify-content: space-between;
  align-items: center;
  padding: 0;
}

.home-container {
    border: 7px solid transparent;
    border-radius: 100%;
}

.activelogo {
    border-color: rgb(68, 68, 67)
}

.logo {
  width: 70px;
  height: 70px;
  background-color: rgb(54, 52, 46);
  border-radius: 50%;
  border: 2px solid rgb(152, 117, 51);
}

@media (max-width: 640px) {

    .link-container {
        flex-direction: column;
    }

    ul {
        flex-direction: column;
        gap: 2rem;
        align-items: flex-start; 
    }
}

.link-container {
  display: flex;
  gap: 2em;
}


.pages {
  text-decoration: none;
  color: rgb(152, 117, 51);
  padding: 0.5rem 1rem;
  background-color: rgb(54, 52, 46);
  border-radius: 10px;
  border: 1px solid transparent;
}

.pages:hover {
  background-color: rgb(68, 68, 68);
  border-color: rgb(152, 117, 51);
}

.active {
  background-color: rgb(68, 68, 68);
  border-color: rgb(152, 117, 51);
}

img {
  object-fit: fill;
  overflow: hidden;
  width: 100%;
  height: 100%;
}
</style>
