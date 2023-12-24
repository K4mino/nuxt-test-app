
<script lang="ts" setup>
import { ref, onBeforeMount } from "vue";

const headerColor = ref("#3498db");
const router = useRouter();

const updateHeaderColor = () => {
  headerColor.value =
    router.currentRoute.value.path === "/" ? "#3498db" : "#2ecc71";
};

onBeforeMount(() => {
  updateHeaderColor();
});

router.afterEach(() => {
  updateHeaderColor();
});
</script>

<template>
  <div class="nav" :style="{ backgroundColor: headerColor }">
    <div class="nav-item">
      <NuxtLink class="nav-link" to="/">Home</NuxtLink>
    </div>
    <div class="nav-item">
      <NuxtLink class="nav-link" to="/SecondPage">Second Page</NuxtLink>
    </div>
  </div>
</template>


<style>
.nav {
  position: relative;
  height: 120px;
  display: flex;
  width: 100%;
  background: transparent;
  justify-content: center;
  gap: 15px;
  align-items: center;
}

.nav-link {
  text-decoration: none;
  color: black;
  font-weight: 700;
  font-size: 24px;
}

.nav-link:hover {
  text-decoration: underline;
}

.nav::after {
  content: "";
  display: block;
  height: 2px;
  background: black;
  width: 100%;
  position: absolute;
  bottom: 0;
}
</style>