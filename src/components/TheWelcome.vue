<script setup>
import { ref } from "vue";
const count = ref(1);
const increase = () => {
  count.value++;
  console.log("count", count.value);
};
const reduce = () => {
  count.value--;
  console.log("count", count.value);
};
const submitForm = (e) => {
  // e.preventDefault(); ngăn chặn sự kiện mặc định của form tránh reload trang
  count.value += 100;
};
</script>

<template>
  <div>Count: {{ count }}</div>
  <button v-on:click="increase">Increase</button>
  <button @click="reduce">Reduce</button>
  <form @submit.prevent="submitForm">
    <button type="submit">Increase x100</button>
  </form>
</template>

<style scoped></style>
