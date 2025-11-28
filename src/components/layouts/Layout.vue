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
  padding: 2rem;

}
</style>
