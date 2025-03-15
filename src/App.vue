<script setup>
import { ref, reactive } from "vue";
import Card from "./components/Card.vue";
import Listings from "./components/Listings.vue";
import roleData from "./assets/data.json";
const roles = ref(roleData);
</script>

<template>
  <div class="nav-section-container">
    <div class="title-container">
      <!-- <h1>Welcome to Dev Roles</h1> -->
    </div>
    <div class="search-field-container">
      <input type="text" />
    </div>
    <!-- <h1 class="text-3xl font-bold underline">Hello from vue</h1> -->
  </div>
  <Listings :roles="roles" />
  <!-- <Card /> -->
</template>

<style lang="scss">
// $secondary-color: #2985a9;

// .container {
//   padding: 20px;
//   background-color: $secondary-color;
//   h1 {
//     color: rgb(153, 30, 30);
//   }
// }
// .nav-section-container {
//   display: flex;
//   justify-content: center;
//   align-items: center;
//   flex-direction: column;
//   background-color: $secondary-color;
//   width: 50%;
//   margin: auto;
// }
</style>
