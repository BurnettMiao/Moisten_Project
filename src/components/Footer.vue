<script setup>
import { ref } from 'vue'

import qrCodeImg from '@/assets/img/qrCode.svg'

// Footer Section 請在此處加入圖片連結文字 ↓↓↓↓↓
const footer = ref({
  logo: 'Moisten',
  igLink: 'https://www.instagram.com/frau_aus_tee/',
  fbLink: 'https://www.instagram.com/frau_aus_tee/',
  aboutUs: {
    title: '關於我們',
    content: [
      // 第一段
      '我們從一間小小的公寓廚房出發，',
      // 第二段
      '邀請你透過味覺與感官，',
      // 第三段
      '重新看見生活裡那些被忽略的關係與議題。',
      // 第四段
      '關於土地、飲食、身體，與我們自己。',
    ],
  },
  contactUs: {
    title: '聯絡我們',
    address: '台北市中正區重陽北路430號5樓',
    phone: '0987-654-321',
    mail: 'helloMisten@gmail.com',
  },
  qrCode: qrCodeImg,
  footer: 'Copyright © 2025 Moisten. All rights reserved.',
})
// Footer Section 請在此處加入圖片連結及文字 ↑↑↑↑↑
</script>

<template>
  <div
    id="contact-section"
    class="bg-moisten-orange pt-[55px] pb-[35px] text-white px-4 xl:px-0 scroll-mt-[100px]"
  >
    <div class="max-w-7xl mx-auto flex flex-wrap gap-12 xl:gap-6 items-stretch justify-between">
      <div class="flex flex-col items-stretch justify-between gap-8 xl:gap-0">
        <div class="font-bold text-[40px] leading-10">{{ footer.logo }}</div>

        <div class="flex items-center gap-2">
          <a :href="footer.igLink" target="_blank"
            ><i class="ri-facebook-box-fill text-4xl xl:text-5xl"></i
          ></a>
          <a :href="footer.fbLink" target="_blank"
            ><i class="ri-instagram-fill text-4xl xl:text-5xl"></i
          ></a>
        </div>
      </div>

      <div class="flex flex-col gap-4 xl:gap-9">
        <div class="font-bold text-2xl">{{ footer.aboutUs.title }}</div>
        <div class="flex flex-col gap-2">
          <div v-for="(item, index) in footer.aboutUs.content" :key="index">{{ item }}</div>
        </div>
      </div>

      <div class="flex flex-col gap-4 xl:gap-9">
        <div class="font-bold text-2xl">{{ footer.contactUs.title }}</div>
        <div class="flex items-start flex-col gap-2">
          <div class="flex items-center gap-3">
            <i class="ri-map-pin-line text-xl"></i> <span>{{ footer.contactUs.address }}</span>
          </div>
          <div class="flex items-center gap-3">
            <i class="ri-phone-line text-xl"></i> <span>{{ footer.contactUs.phone }}</span>
          </div>
          <div class="flex items-center gap-3">
            <i class="ri-mail-line text-xl"></i> <span>{{ footer.contactUs.mail }}</span>
          </div>
        </div>
      </div>

      <div class="flex self-end max-w-[135px] max-h-[135px] p-2">
        <img class="w-full h-full" :src="footer.qrCode" alt="" />
      </div>
    </div>

    <div class="text-sm text-center mt-[55px]">{{ footer.footer }}</div>
  </div>
</template>

<style scoped>
#contact-section {
  font-family: var(--font-moisten-libre-baskerville);
}
</style>
