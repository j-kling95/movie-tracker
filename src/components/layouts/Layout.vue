<script setup>
import Navbar from "../Navbar.vue";
</script>

<template>
  <div class="layout">
    <header>
      <Navbar />
    </header>
    <main>
      <slot />
    </main>
    <footer></footer>
  </div>
</template>

<style scoped>
.layout {
  padding: 1rem 2rem;
  
}

header,
footer,
main {
  max-width: 700px;

}

main {
    padding: 2rem 0;
}
</style>
