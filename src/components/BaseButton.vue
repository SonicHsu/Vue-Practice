<template>
  <button
    class="bg-gray-400 rounded-sm px-2 cursor-pointer text-white text-xl"
    @click="$emit('click')"
  >
    <slot />
  </button>
</template>