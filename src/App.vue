<script setup>
import "./style.css";
import { ref } from "vue";
import BaseButton from "./components/BaseButton.vue";
import { campingItems } from "./data/campingItems";

const count = ref(0);

const webTitle = ref("Camping is life");
const webSubtitle = ref("");
const titleColor = ref("text-white");
const text = ref("");
const campingItemsObjects = ref(campingItems);

function handleClick(msg) {
  webSubtitle.value = msg;
  titleColor.value = msg;
  handleColorChange();
}

const isTextRed = ref(false);
const isTextBlue = ref(false);

function handleColorChange() {
  isTextRed.value = titleColor.value === "text-red-500";
  isTextBlue.value = titleColor.value === "text-blue-500";
}

function addItem(){
campingItemsObjects.value.push({id:campingItemsObjects.value.length+1 , name:text.value , category:text.value, price:text.value})

text.value = ''
}

</script>

<template>
  <div
    class="text-white h-screen bg-[url('./public/camping-bg.jpg')] bg-cover bg-center"
  >
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
      <p class="text-white">{{ text }}</p>
      <div class="flex text-center items-center justify-center my-6"> 
        <input
          v-model="text"
          placeholder="Type here"
          class="text-white  px-4 py-2 rounded bg-white/20"
        />
        <button class="w-[200px] h-full bg-blue-500 cursor-pointer"  @click="addItem()">Add item Button</button>
      </div>

      <p v-if="isTextRed">the Text is Red</p>
      <p v-else-if="isTextBlue">the Text is Blue</p>
      <p v-else>the Text is Green</p>

      <ul>
        <li v-for="object in campingItemsObjects" :key="object.id">
          {{ object.name }} - {{ object.price }}
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped></style>
