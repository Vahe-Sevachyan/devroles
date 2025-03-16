<script setup>
import { ref, reactive, onMounted } from "vue";
// import Card from "./components/Card.vue";
import Listings from "./components/Listings.vue";
import roleData from "../public/data.json";
// const roles = ref(roleData);
const roles = ref([]);

onMounted(() => {
  roles.value = roleData; // Assign the data after mounting
});
</script>

<template>
  <div
    class="w-full h-30 bg-[url('../public/images/bg-header-desktop.svg')] bg-no-repeat bg-center bg-cover"
  >
    <div class="flex items-center justify-center pt-2">
      <h1
        class="text-4xl md:text-6xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-gray-600 to-gray-900 relative mt-4"
      >
        Welcome to Dev Roles
        <span
          class="absolute inset-0 blur-md opacity-60 bg-gradient-to-r from-gray-600 to-gray-900"
        ></span>
      </h1>
    </div>

    <!-- <div class="flex items-center justify-center mt-6">
      <input
        type="text"
        placeholder="Enter text..."
        class="w-80 px-4 py-2 text-white bg-[#4C4D4C] border border-gray-600 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 transition duration-300 shadow-md"
      />
    </div> -->
  </div>
  <!-- <Listings :roles="roles" class="bg-[#EEF6F6]" /> -->

  <Listings :roles="roles" class="bg-[#EEF6F6]" />
</template>

<style lang="scss">
// $secondary-color: #2985a9;
div {
  font-family: "Poppins", Geneva, Tahoma, sans-serif;
}
// .container {
//   padding: 20px;
//   background-color: $secondary-color;
//   h1 {
//     color: rgb(153, 30, 30);
//   }
// }
</style>
