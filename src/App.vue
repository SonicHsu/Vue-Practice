<script setup>
import "./style.css";
import { ref } from "vue";
const count = ref(0);
</script>

<template>
  <div class="h-screen bg-[url('./public/camping-bg.jpg')] bg-cover bg-center">
    <div class="flex flex-col items-center justify-center h-full bg-black/50">
      <h1 class="text-white text-5xl font-bold">Camping</h1>

      <header class="w-screen flex justify-center mt-5">
        <nav class="space-x-5">
          <button
            class="bg-gray-400 rounded-sm px-2 cursor-pointer text-white text-xl"
            @click=""
          >
            Button01
          </button>
          <button
            class="bg-gray-400 rounded-sm px-2 cursor-pointer text-white text-xl"
            @click=""
          >
            Button02
          </button>
        </nav>
      </header>
    </div>
  </div>
</template>

<style scoped></style>
