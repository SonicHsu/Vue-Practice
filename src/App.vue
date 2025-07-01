<script setup>
import "./style.css";
import { ref } from "vue";
const count = ref(0);
</script>

<template>
  <h1 class="text-3xl">{{ count }}</h1>
  <header>
    <nav>
      <button
        class="bg-blue-400 rounded-xl px-2 cursor-pointer text-white"
        @click="count--"
      >
        Button01
      </button>
      <button
        class="bg-blue-400 rounded-xl px-2 cursor-pointer text-white"
        @click="count++"
      >
        Button01
      </button>
    </nav>
  </header>
</template>

<style scoped></style>
