<script setup>
import { ref } from 'vue'

// 請在此處加入圖片連結，影片連結及文字 ↓↓↓↓↓
const imgAndTextArr = ref([
  // 圖片連結及文字寫法
  {
    img: 'https://images.unsplash.com/photo-1593335663758-4da70281a917?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    text: 'Moisten',
  },
  {
    img: 'https://images.pexels.com/photos/1240961/pexels-photo-1240961.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2',
    text: 'Moisten',
  },
  // 影片連結及文字寫法
  {
    video: 'https://videos.pexels.com/video-files/3255109/3255109-uhd_2560_1440_25fps.mp4',
    text: 'Moisten',
  },
])
// 請在此處加入圖片連結，影片連結及文字 ↑↑↑↑↑

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
      <!-- 判斷是否有 img 屬性 -->
      <img
        v-if="item.img"
        class="w-full h-full object-cover object-center"
        :src="item.img"
        alt=""
      />
      <!-- 判斷是否有 video 屬性 -->
      <video
        v-else-if="item.video"
        autoplay
        loop
        muted
        playsinline
        class="w-full h-full object-cover object-center"
      >
        <source :src="item.video" type="video/mp4" />
      </video>

      <span
        class="absolute top-1/2 left-1/2 z-10 text-[64px] xl:text-8xl text-white font-bold opacity-90 -translate-x-1/2 -translate-y-1/2 hero-text"
        >{{ item.text }}</span
      >
    </swiper-slide>
  </swiper>
</template>

<style scoped>
.hero-text {
  font-family: var(--font-moisten-libre-baskerville);
}

:deep(.swiper-pagination-bullet) {
  background: var(--color-moisten-orange) !important;
}
</style>
