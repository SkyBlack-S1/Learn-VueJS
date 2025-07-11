<script setup>
import { useRouter, useRoute } from "vue-router";
const router = useRouter(); // Lấy đối tượng điều hướng (router)
const route = useRoute(); // 	Lấy thông tin của route hiện tại (params, query, path,...)
console.log("path", route.path);
console.log("name", route.name);
console.log("params", route.params);
console.log("query", route.query);
</script>
<template>
  <div class="about">
    <!-- Cách 1 -->
    <!-- <button @click="router.push({ name: 'user' })">Redirect About User</button> -->
    <!-- <button @click="router.push({ path: '/about/user' })">
      Redirect About User
    </button> -->
    <!-- Cách 2 -->
    <RouterLink to="/about/user">Redirect About User</RouterLink>
    <router-view></router-view>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
