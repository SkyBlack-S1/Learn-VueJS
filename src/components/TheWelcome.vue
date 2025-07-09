<script setup>
import { ref } from "vue";

const textInput = ref("");
console.log("Rerender Component", textInput.value);

const name = ref("");
</script>

<template>
  <div>Text: {{ textInput }}</div>
  <input type="text" v-model="textInput" />
  <br />
  <input v-model.trim="name" placeholder="Nhập tên của bạn" />
  <p>Xin chào {{ name }}!</p>
</template>

<style scoped></style>
