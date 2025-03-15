<template>
  <div class="flex items-center justify-center min-h-screen bg-gray-900">
    <div
      class="bg-white p-3.5 rounded-2xl shadow-lg w-175 text-center flex items-center justify-between"
    >
      <div class="flex items-center" v-for="role in roles" :key="role.id">
        <img :src="role.logo" alt="" class="size-15 mr-2" />
        <div class="flex-row-reverse">
          <div class="flex items-center justify-start w-60 border-1">
            <span class="mr-2">{{ role.company }}</span>
            <span class="mr-2">{{ role.new }}</span>
            <span>{{ role.featured }}</span>
          </div>
          <div class="flex items-center justify-start w-60 border-1">
            <span>{{ role.company }}</span>
            <span>{{ role.new }}</span>
            <span>{{ role.featured }}</span>
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
      </div>
      <div class="flex items-center justify-around w-60">
        <span
          v-for="(language, index) in roles.languages"
          :key="index"
          class="bg-gray-200 text-orange-300 px-2 py-1 rounded-full mr-2"
        >
          {{ language }}
        </span>
      </div>
      <!-- <div class="flex items-center justify-around w-60">
        <span v-for="language in roles.languages" :key="language">{{
          language
        }}</span>

        <span>Vuejs</span>
        <span>JavaScript</span>
        <span>Python</span>
      </div> -->
    </div>
  </div>
</template>
<script setup>
import { defineProps } from "vue";
defineProps({
  roles: Array,
});
</script>
<style scoped></style>
