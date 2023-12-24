<template>
  <div class="accordion">
    <h2>Accordion</h2>
    <div
      v-for="(item, index) in items"
      :key="index"
      @click="toggleItem(index)"
      class="accordion-item"
    >
      <div class="accordion-header">{{ item.header }}</div>
      <div v-show="item.open" class="accordion-content">{{ item.content }}</div>
    </div>
  </div>
</template>
  
  <script setup>
import { ref } from "vue";

const items = ref([
  { header: "Section 1", content: "Content for section 1", open: false },
  { header: "Section 2", content: "Content for section 2", open: false },
]);

const toggleItem = (index) => {
  items.value[index].open = !items.value[index].open;
};
</script>
  
  <style scoped>
.accordion {
  width: 500px;
}

.accordion-item {
  cursor: pointer;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.accordion-header {
  padding: 1rem;
  background-color: #f0f0f0;
  font-weight: bold;
}

.accordion-content {
  padding: 1rem;
}
</style>
  