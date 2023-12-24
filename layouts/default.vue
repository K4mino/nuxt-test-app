<script lang="ts" setup>
import Footer from "../components/Footer.vue";
import Header from "../components/Header.vue";
</script>

<template>
  <div class="container">
    <Header />
    <slot />
    <Footer />
  </div>
</template>

<style>
body {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100vh;
}
</style>