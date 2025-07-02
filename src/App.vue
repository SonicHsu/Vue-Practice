<script setup>
import "./style.css";
import { ref } from "vue";
import BaseButton from './components/BaseButton.vue';
const count = ref(0);

function handleClick(msg) {
  console.log('點擊了按鈕：', msg);
}
</script>

<template>
  <div class="h-screen bg-[url('./public/camping-bg.jpg')] bg-cover bg-center">
    <div class="flex flex-col items-center justify-center h-full bg-black/50">
      <h1 class="text-white text-5xl font-bold">Camping</h1>

      <header class="w-screen flex justify-center mt-5">
        <nav class="space-x-5">
          <BaseButton @click="handleClick('Button01')">Button01</BaseButton>
          <BaseButton @click="handleClick('Button02')">Button02</BaseButton>
          <BaseButton @click="handleClick('Button03')">Button03</BaseButton>
        </nav>
      </header>
    </div>
  </div>
</template>

<style scoped></style>
