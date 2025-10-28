<script setup>
// Store Section 請在此處加入圖片連結文字 ↓↓↓↓↓
const store = {
  title: 'Vist Our Store',
  img: 'https://frauaustee.co.uk/moisten_images/store_section.jpg',
  link: 'https://www.google.com.tw',
  linkText: '即刻前往',
}
// Store Section 請在此處加入圖片連結及文字 ↑↑↑↑↑
</script>

<template>
  <div
    id="store-section"
    class="bg-moisten-white max-w-7xl mx-auto max-h-[350px] mt-[55px] xl:mt-[110px] mb-[55px] flex items-center justify-center relative px-4 scroll-mt-[100px]"
  >
    <img
      class="absolute top-0 left-0 w-full h-full object-cover object-center"
      :src="store.img"
      alt=""
    />

    <div
      class="relative z-10 flex flex-col items-center justify-center gap-[25px] py-[112px] store-content"
    >
      <div class="text-[30px] xl:text-4xl text-white font-bold">{{ store.title }}</div>
      <a
        :href="store.link"
        target="_blank"
        class="inline-block px-[25px] py-[16px] border border-white rounded-4xl text-white text-lg xl:text-xl hover:bg-white hover:text-moisten-text duration-500 cursor-pointer"
      >
        {{ store.linkText }}
      </a>
    </div>
  </div>
</template>

<style scoped>
.store-content {
  font-family: var(--font-moisten-libre-baskerville);
}
</style>
