<!-- Parent -->
<script setup>
import { computed, onMounted, ref, watch } from "vue";
import TheWelcome from "../components/TheWelcome.vue";
import HelloWorld from "@/components/HelloWorld.vue";

const count = ref(10);

const handleIncrease = (data) => {
  // data là object { label: "Hello", value: 5 }
  count.value += data.value;
  console.log(`Increase by ${data.label}`);
};

const categoryProduct = ref("food");

const products = ref([
  { id: 1, name: "Pizza", category: "food", price: 100 },
  { id: 2, name: "Hamburger", category: "food", price: 200 },
  { id: 3, name: "Milk", category: "drink", price: 300 },
  { id: 4, name: "Tea", category: "drink", price: 400 },
  { id: 5, name: "Juice", category: "drink", price: 500 },
]);

const todos = ref([]);

const showHelloWorld = ref(true);

const handChangeCategoryProduct = (value) => {
  categoryProduct.value = value;
};

const productsFilter = computed(() => {
  return products.value.filter(
    (item) => item.category === categoryProduct.value
  );
});

onMounted(() => {
  // Hàm này luôn chạy sau template
  fetch("https://jsonplaceholder.typicode.com/todos")
    .then((response) => response.json())
    .then((json) => (todos.value = json));
  showHelloWorld.value = false;
});

watch([showHelloWorld, todos], (newValue, oldValue) => {
  console.log("newValue:", newValue);
  console.log("oldValue:", oldValue);
  console.log("Todos has changed");
});
</script>

<template>
  <main>
    <div v-if="showHelloWorld">
      <HelloWorld msg="Hello SkyBlack" />
    </div>
    <button @click="showHelloWorld = false">Remove Component HelloWorld</button>
    <button @click="showHelloWorld = true">Restore Component HelloWorld</button>
  </main>
</template>

<style scoped>
div {
  font-weight: 600;
}
</style>
