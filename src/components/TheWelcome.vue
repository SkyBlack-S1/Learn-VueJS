<script setup>
// Logic code
const message = "Welcome to Vue.js Project Basic!";
const a = 100;
const array = [1, 2, 3, 4, 5];
const user = {
  name: "Dinh Van Thuan",
  age: 30,
};
console.log(message);
</script>

<template>
  <div class="red">{{ message }} {{ user }}</div>
  <div class="blue">
    {{ user.name }} <br />
    {{ user.age }}
  </div>
</template>

<style scoped>
.red {
  color: red;
  font-size: 20px;
  font-weight: bold;
}
.blue {
  color: blue;
  font-size: 18px;
  font-weight: normal;
}
</style>
