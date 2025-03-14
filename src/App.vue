<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import TheWelcome from "./components/TheWelcome.vue";
</script>

<template>
  <div class="bg-green-500 p-4 text-white">
    <p class="text-xl">Hello, Vue with Tailwind and SASS!</p>
  </div>
</template>

<style lang="scss" scoped>
$primary-color: #94a99e;

p {
  color: $primary-color;
  font-weight: bold;
}
</style>
