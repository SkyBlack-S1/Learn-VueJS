<!-- Parent -->
<script setup>
import { ref } from "vue";
import TheWelcome from "../components/TheWelcome.vue";

const count = ref(10);

const handleIncrease = (data) => {
  // data là object { label: "Hello", value: 5 }
  count.value += data.value;
  console.log(`Increase by ${data.label}`);
};
</script>

<template>
  <main>
    <TheWelcome :countView="count" @handle-increase="handleIncrease" />
  </main>
</template>
