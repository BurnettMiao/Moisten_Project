<script setup>
import { ref, watch } from 'vue'
import SmallMenu from '@/components/utility/SmallMenu.vue'

// Navbar Section 請在此處加入圖片連結文字 ↓↓↓↓↓
const navItems = ref([
  { text: '關於我們', target: 'introduce-section' },
  { text: '我們目標', target: 'goals-section' },
  { text: '活動紀錄', target: 'event-section' },
  { text: '商店', target: 'store-section' },
  { text: '常見問題', target: 'qa-section' },
  { text: '聯絡我們', target: 'contact-section' },
])
// Navbar Section 請在此處加入圖片連結文字 ↑↑↑↑↑

const oepnMenu = ref(false)

const toggleMenu = () => {
  oepnMenu.value = !oepnMenu.value
}

// 滾動到指定 section
const scrollToSection = (targetId) => {
  const element = document.getElementById(targetId)
  if (element) {
    element.scrollIntoView({
      behavior: 'smooth',
      block: 'start',
    })
  }
  // 關閉手機選單
  oepnMenu.value = false
}

// 用 watch 監聽選單狀態變化
watch(oepnMenu, (newVal) => {
  if (newVal) {
    document.body.style.overflow = 'hidden'
  } else {
    document.body.style.overflow = 'auto'
  }
})
</script>

<template>
  <nav class="hidden w-full md:flex items-center justify-center gap-12 py-[20px] fixed z-50">
    <div class="bg-white/25 flex py-[10px] px-[20px] rounded-4xl gap-12 shadow-md">
      <span
        v-for="(item, index) in navItems"
        :key="index"
        @click="scrollToSection(item.target)"
        class="text-white opacity-100 cursor-pointer font-bold text-lg hover:text-moisten-orange"
        >{{ item.text }}</span
      >
    </div>
  </nav>

  <nav @click="toggleMenu" class="fixed block md:hidden top-5 right-5 text-white z-90">
    <i
      class="text-3xl cursor-pointer"
      :class="oepnMenu ? 'ri-close-line text-moisten-text' : 'ri-menu-line'"
    ></i>
  </nav>
  <SmallMenu v-if="oepnMenu" :navItems="navItems" @scroll-to="scrollToSection" />
</template>
