<!-- Child -->
<script setup>
const props = defineProps(["countView"]);
const emit = defineEmits(["handle-increase"]);
const onIncrease = () => {
  emit("handle-increase", { label: "Hello", value: 5 }); // Truyền cho cha
};
</script>

<template>
  <div>Count: {{ props.countView }}</div>
  <button @click="onIncrease">Increase</button>
</template>

<style scoped></style>
