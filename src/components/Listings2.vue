<template>
  <div class="flex items-center justify-center min-h-screen bg-gray-900">
    <div class="bg-white p-3.5 rounded-2xl shadow-lg w-175 text-center">
      <div
        v-for="role in roles"
        :key="role.id"
        class="flex items-center justify-between"
      >
        <img :src="role.logo" alt="Company Logo" class="size-15 mr-2" />

        <div class="flex-row-reverse">
          <div class="flex items-center justify-start w-60 border-1">
            <span class="mr-2">{{ role.company }}</span>
            <span
              v-if="role.new"
              class="mr-2 bg-green-500 text-white px-2 py-1 rounded"
              >New</span
            >
            <span
              v-if="role.featured"
              class="bg-gray-700 text-white px-2 py-1 rounded"
              >Featured</span
            >
          </div>
          <h2 class="flex text-xl font-semibold text-gray-800 justify-start">
            {{ role.position }}
          </h2>
          <div class="flex items-center justify-start w-70 border-1">
            <span class="mr-2">{{ role.postedAt }}</span>
            <span class="mr-2">{{ role.contract }}</span>
            <span>{{ role.location }}</span>
          </div>
        </div>

        <!-- Display Languages -->
        <div class="flex items-center justify-around w-60">
          <span
            v-for="(language, index) in role.languages"
            :key="index"
            class="bg-gray-500 text-orange-300 px-2 py-1 rounded-full mr-2"
          >
            {{ language }}
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  roles: Array,
});
</script>
