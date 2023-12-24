<template>
  <label class="custom-checkbox" :class="{ checked: isChecked }">
    <input
      class="checkbox"
      type="checkbox"
      v-model="isChecked"
      @change="handleChange"
    />
    <span class="checkmark"></span>
    {{ label }}
  </label>
</template>
  
<script setup>
import { ref } from "vue";
defineProps({
  label: String,
});

const isChecked = ref(false);

const handleChange = () => {};
</script>
  
  <style scoped>
.checkbox {
  display: none;
}
.custom-checkbox {
  display: flex;
  align-items: center;
  cursor: pointer;
  user-select: none;
}

.checkmark {
  width: 20px;
  height: 20px;
  border: 1px solid #ccc;
  border-radius: 3px;
  margin-right: 8px;
  position: relative;
}

.checkmark::after {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 10px;
  height: 10px;
  background-color: #2196f3;
  border-radius: 2px;
  display: none;
}

.checked .checkmark::after {
  display: block;
}
</style>
  