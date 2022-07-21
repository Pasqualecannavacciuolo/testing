<script setup>
import { RouterLink, RouterView } from 'vue-router';
</script>

<script>
export default {
  mounted() {
    // Creo un array di elementi che hanno la seguente classe '.menu-item'
    let menu_items = document.querySelectorAll('.menu-item');
    menu_items.forEach(element => {
      // Quando il mouse entra nel campo della voce del menu
      element.addEventListener("mouseenter", () => {
        element.classList.add("animate__animated");
        element.classList.add("animate__pulse");
      });
      // Quando il mouse esce nel campo della voce del menu
      element.addEventListener("mouseleave", () => {
        element.classList.remove("animate__animated");
        element.classList.remove("animate__pulse");
      });
    });
  }
}
</script>

<template>

  <nav class="navbar navbar-expand-lg bg-light">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">
        <img alt="Vue logo" class="logo" src="@/assets/psychology.png" width="45" height="35" />
      </a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
        aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item fs-6 fw-bold">
            <a class="nav-link">
              <RouterLink class="nav-link text-dark menu-item" to="/">Home</RouterLink>
            </a>
          </li>
          <li class="nav-item fs-6 fw-bold">
            <a class="nav-link">
              <RouterLink class="nav-link text-dark menu-item" to="/about">About</RouterLink>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <RouterView />
</template>

<style>
.nav-link {
  font-family: 'Poppins', sans-serif;
}

.animate__animated.animate__pulse {
  --animate-duration: 1s;
}
</style>
