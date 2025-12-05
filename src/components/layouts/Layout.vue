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
    <footer>
      <p>this page was created by</p>
      <div class="footer-container">
        <img
          class="profile-picture"
          src="../../assets/73388817.jpg"
          alt="profile_picture"
        />
        <a href="https://github.com/j-kling95">@j-kling95</a>
        <i class="fa-brands fa-github"></i>
      </div>
    </footer>
  </div>
</template>

<style scoped>
.layout {
    display: flex;
    flex-direction: column;
}

main,
header,
footer {
  padding: 1rem 2rem 0;
  border-radius: inherit;
  background-color: inherit;
}

header {
    max-height: fit-content;
    z-index: 2;
    position: sticky;
    top: 0;
}

footer {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  align-items: center;
}
.footer-container {
  display: flex;
  gap: 1rem;
  padding: 0.5rem 1rem;
  justify-content: center;
  align-items: center;
  border: 1px solid transparent;
  border-radius: 20px;
}

.footer-container:hover {
  border: 1px solid rgb(152, 117, 51);
}

.footer-container a {
  text-decoration: none;
}

.footer-container a:visited {
  color: rgb(255, 255, 255);
}

i {
  font-size: 35px;
  color: rgb(195, 134, 19);
}

.profile-picture {
  width: 50px;
  height: 50px;
  border-radius: 100%;
}
</style>
