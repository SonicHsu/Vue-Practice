<script setup>
import "./style.css";
import { ref } from "vue";
import BaseButton from "./components/BaseButton.vue";
const count = ref(0);

const webTitle = ref("Camping is life");
const webSubtitle = ref("");
const titleColor = ref("text-white");
const text = ref('')

function handleClick(msg) {
  webSubtitle.value = msg;
  titleColor.value = msg;
}

function onInput(e) {
  text.value = e.target.value
}
</script>

<template>
  <div class="h-screen bg-[url('./public/camping-bg.jpg')] bg-cover bg-center">
    <div class="flex flex-col items-center justify-center h-full bg-black/50">
      <h1 class="text-white text-5xl font-bold">{{ webTitle }}</h1>
      <h2 v-bind:class="['mt-6', titleColor]">{{ webSubtitle }}</h2>

      <header class="w-screen flex justify-center mt-5">
        <nav class="space-x-5">
          <BaseButton @click="handleClick('text-red-500')">Button01</BaseButton>
          <BaseButton v-on:click="handleClick('text-blue-500')"
            >Button02</BaseButton
          >
          <BaseButton @click="handleClick('text-green-500')"
            >Button03</BaseButton
          >
        </nav>
      </header>
      <p class="text-white">{{text}}</p>
      <input v-model="text" placeholder="Type here" class="text-white  mt-6 px-4 py-2 rounded bg-white/20" />
    </div>
  </div>
</template>

<style scoped></style>
