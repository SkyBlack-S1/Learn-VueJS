<script setup>
import { reactive, ref } from "vue";
// ref sử dụng 1 đối tượng và 1 thuộc tính
// truy cập thuộc tính bằng cách .value
const count = ref(0);
count.value = count.value + 1;

// reactive sử dụng 1 đối tượng, trong đó có nhiều thuộc tính
// truy cập thuộc tính bằng cách .thuộc_tính
const count1 = reactive({
  title: "Hello World",
  author: "Dinh Van Thuan",
  age: 18,
});

count1.age += 1;
console.log("count1", count1.title, count1.author, count1.age);
</script>

<template>
  <div class="red">This is {{ count }}</div>
  <div class="blue">
    This is {{ count1.title }} {{ count1.author }} {{ count1.age }}
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
