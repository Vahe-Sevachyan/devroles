<script setup>
import { ref, reactive, onMounted } from "vue";

import Listings from "./components/Listings.vue";
import roleData from "./data.json";

// import bgHeader from "../public/images/bg-header-desktop.svg";
// const roles = ref(roleData);
const roles = ref([]);

onMounted(() => {
  roles.value = roleData; // Assign the data after mounting
});
</script>

<template>
  <div
    class="w-full hero h-30 bg-[url('/images/bg-header-desktop.svg')] bg-no-repeat bg-center bg-cover"
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
  </div>
  <Listings :roles="roles" class="bg-[#EEF6F6]" />
</template>

<style lang="scss">
div {
  font-family: "Poppins", Geneva, Tahoma, sans-serif;
}
</style>
