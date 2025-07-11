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

const products = ref([
  { id: 1, name: "Pizza", price: 100 },
  { id: 2, name: "Cafe", price: 200 },
  { id: 3, name: "Milk", price: 300 },
]);
</script>

<template>
  <main>
    <TheWelcome :countView="count" @handle-increase="handleIncrease" />
  </main>
  <div>
    <div v-for="product in products">
      <div>
        <div>{{ product.name }} {{ product.price }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
div {
  font-weight: 600;
}
</style>
