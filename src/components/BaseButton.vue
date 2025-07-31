<template>
  <button
    class="bg-gray-800 rounded-lg px-2 cursor-pointer text-white text-xl hover:bg-gray-400"
    @click="$emit('click')"
  >
    <slot />
  </button>
</template>