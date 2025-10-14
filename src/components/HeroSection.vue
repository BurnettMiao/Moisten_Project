<script setup>
import { ref } from 'vue'

const imgAndTextArr = ref([
  {
    img: 'https://images.unsplash.com/photo-1593335663758-4da70281a917?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    text: 'Moisten',
  },
])

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue'

// Import Swiper styles
import 'swiper/css'

import 'swiper/css/pagination'

// import required modules
import { Pagination, Autoplay } from 'swiper/modules'

const modules = [Pagination, Autoplay]
</script>

<template>
  <swiper
    :pagination="{
      dynamicBullets: true,
    }"
    :autoplay="{
      delay: 5000,
      disableOnInteraction: false,
    }"
    :loop="true"
    :modules="modules"
    class="w-full h-[95vh]"
  >
    <swiper-slide
      v-for="(item, index) in imgAndTextArr"
      :key="index"
      class="w-full h-full relative"
    >
      <img class="w-full h-full object-cover object-center" :src="item.img" alt="" />
      <span
        class="absolute top-1/2 left-1/2 z-10 text-[64px] xl:text-8xl text-white font-bold opacity-90 -translate-x-1/2 -translate-y-1/2 hero-text"
        >{{ item.text }}</span
      >
    </swiper-slide>
    <swiper-slide class="w-full h-full relative">
      <video autoplay loop muted playsinline class="w-full h-full object-cover object-center">
        <source
          src="https://video.wixstatic.com/video/11062b_40811fcc9cac4a5bbfb0d93aaa94d70d/720p/mp4/file.mp4"
          type="video/mp4"
        />
      </video>
      <span
        class="absolute top-1/2 left-1/2 z-10 text-[64px] xl:text-8xl text-white font-bold opacity-90 -translate-x-1/2 -translate-y-1/2 hero-text"
        >Moisten</span
      >
    </swiper-slide>
  </swiper>
</template>

<style scoped>
.hero-text {
  font-family: inter, sans-serif;
}

:deep(.swiper-pagination-bullet) {
  background: var(--color-moisten-orange) !important;
}
</style>
