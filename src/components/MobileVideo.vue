<script setup>
// 請在此處加入影片連結文字 ↓↓↓↓↓
const mobileVideo = [
  // 影片連結及文字寫法
  {
    video: 'https://videos.pexels.com/video-files/3255109/3255109-uhd_2560_1440_25fps.mp4',
    text: 'Moisten',
  },
]
// 請在此處加入影片連結及文字 ↑↑↑↑↑
</script>

<template>
  <div class="block sm:hidden w-full h-[95vh]">
    <div v-for="(item, index) in mobileVideo" class="w-full h-full relative" :key="index">
      <video autoplay loop muted playsinline class="w-full h-full object-cover object-center">
        <source :src="item.video" type="video/mp4" />
      </video>
      <span
        class="absolute top-1/2 left-1/2 z-10 text-[64px] xl:text-8xl text-white font-bold opacity-90 -translate-x-1/2 -translate-y-1/2 hero-text"
        >{{ item.text }}</span
      >
    </div>
  </div>
</template>

<style scoped>
.hero-text {
  font-family: var(--font-moisten-libre-baskerville);
}
</style>
