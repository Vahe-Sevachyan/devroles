<template>
  <div class="flex items-center justify-center">
    <div class="text-center">
      <!-- 🔽 Filter Section -->
      <div
        class="mb-4 p-4 bg-[#F9FBFB] shadow-teal-800/60 shadow-lg mt-2 rounded-lg"
      >
        <h3 class="text-lg font-bold mb-2">Filter by Criteria:</h3>

        <!-- 🔹 Filter by Contract Type -->
        <div class="mb-2">
          <label v-for="contract in contractTypes" :key="contract" class="mr-4">
            <input
              type="checkbox"
              :value="contract"
              v-model="selectedContracts"
            />
            {{ contract }}
          </label>
        </div>
        <!-- 🔹 Filter by Language -->
        <div>
          <label v-for="language in allLanguages" :key="language" class="mr-4">
            <input
              type="checkbox"
              :value="language"
              v-model="selectedLanguages"
            />
            {{ language }}
          </label>
        </div>
      </div>
      <button
        @click="clearFilters"
        class="px-3 py-2 bg-red-500 text-white rounded mt-1 mb-2"
      >
        Clear Filters
      </button>
      <div
        v-for="role in filteredRoles"
        :key="role.id"
        class="flex items-center w-170 bg-[#F9FBFB] shadow-teal-800/60 shadow-lg m-2 p-1.5"
      >
        <img :src="role.logo" alt="Company Logo" class="size-15 m-3" />
        <div class="flex-row-reverse mr-auto">
          <div class="flex items-center justify-start w-60">
            <span class="mr-2">{{ role.company }}</span>
            <span
              v-if="role.new"
              class="mr-2 bg-teal-500 text-white px-2 py-1 rounded"
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
          <div class="flex items-center justify-start w-70">
            <span class="mr-2 text-gray-400">{{ role.postedAt }} - </span>
            <span class="mr-2 text-gray-400">{{ role.contract }} - </span>
            <span class="text-gray-400 font-sans">{{ role.location }}</span>
          </div>
        </div>
        <div class="flex items-center justify-around w-60">
          <span
            v-for="(language, index) in role.languages"
            :key="index"
            class="bg-gray-200 text-teal-600 px-2 py-0.5"
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
import { ref, computed } from "vue";
const props = defineProps({
  roles: Array,
});

// Reactive State for Filters
const selectedContracts = ref([]); // Holds selected contract types
const selectedLanguages = ref([]); // Holds selected languages
const clearFilters = () => {
  selectedContracts.value = [];
  selectedLanguages.value = [];
};
// Get all unique contract types
const contractTypes = computed(() => {
  return [...new Set(props.roles.map((role) => role.contract))];
});

// Get all unique languages
const allLanguages = computed(() => {
  const languagesSet = new Set();
  props.roles.forEach((role) => {
    if (role.languages) {
      role.languages.forEach((lang) => languagesSet.add(lang));
    }
  });
  return [...languagesSet];
});

// Computed: Filtered Roles Based on Selection
const filteredRoles = computed(() => {
  return props.roles.filter((role) => {
    const matchesContract =
      selectedContracts.value.length === 0 ||
      selectedContracts.value.includes(role.contract);

    const matchesLanguage =
      selectedLanguages.value.length === 0 ||
      (role.languages &&
        role.languages.some((lang) => selectedLanguages.value.includes(lang)));

    return matchesContract && matchesLanguage;
  });
});
</script>
