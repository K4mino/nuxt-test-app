<script lang="ts" setup>
import { ref } from "vue";

const drawerOpen = ref(false);
const closeDrawer = () => {
  drawerOpen.value = false;
};

const openDrawer = () => {
  drawerOpen.value = true;
};
</script>

<template>
  <div class="wrapper">
    <button @click="openDrawer">Open drawer</button>
    <div class="drawer" :class="{ show: drawerOpen }">
      <h2>Drawer</h2>
      <slot />
      <button @click="closeDrawer">Close</button>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  position: relative;
}
.drawer {
  width: auto;
  min-width: 300px;
  background-color: slateblue;
  display: flex;
  flex-direction: column;
  height: 100%;
  position: fixed;
  top: 0;
  transform: translateX(-120%);
  transition: transform 0.3s ease;
}

.drawer.show {
  transform: translateX(0);
}
</style>