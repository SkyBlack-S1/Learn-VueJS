<!-- Parent -->
<script setup>
import { computed, ref } from "vue";
import TheWelcome from "../components/TheWelcome.vue";

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

const handChangeCategoryProduct = (value) => {
  categoryProduct.value = value;
};

const productsFilter = computed(() => {
  return products.value.filter(
    (item) => item.category === categoryProduct.value
  );
});
</script>

<template>
  <main>
    <!-- <TheWelcome :countView="count" @handle-increase="handleIncrease" /> -->
    <button @click="handChangeCategoryProduct('food')">Hiển thị food</button>
    <button @click="handChangeCategoryProduct('drink')">Hiển thị drink</button>
    <div v-if="categoryProduct === 'food'">Danh sach Food</div>
    <div v-else-if="categoryProduct === 'drink'">Danh sach Drink</div>

    <div>
      <div v-for="product in productsFilter">
        <div>
          <div>{{ product.name }} {{ product.price }}</div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
div {
  font-weight: 600;
}
</style>
