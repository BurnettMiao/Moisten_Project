<script setup>
import { ref } from 'vue'

const imgAndTextArr = ref([
  {
    img: 'https://images.unsplash.com/photo-1593335663758-4da70281a917?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    text: 'Moisten',
  },
])
</script>

<template>
  <div class="w-full h-[95vh]">
    <div v-for="(item, index) in imgAndTextArr" :key="index" class="w-full h-full relative">
      <img class="w-full h-full object-cover object-center" :src="item.img" alt="" />
      <span
        class="absolute top-1/2 left-1/2 z-10 text-8xl text-white font-bold opacity-90 -translate-x-1/2 -translate-y-1/2 hero-text"
        >{{ item.text }}</span
      >
    </div>
  </div>
</template>

<style scoped>
.hero-text {
  font-family: inter, sans-serif;
}
</style>
