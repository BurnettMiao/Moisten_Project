<script setup>
import { ref } from 'vue'
import SmallMenu from '@/components/SmallMenu.vue'

const navItems = ref(['關於我們', '我們目標', '活動紀錄', '商店', '常見問題', '聯絡我們'])

const oepnMenu = ref(false)

const toggleMenu = () => {
  oepnMenu.value = !oepnMenu.value
}
</script>

<template>
  <nav class="hidden w-full md:flex items-center justify-center gap-12 py-[20px] fixed z-50">
    <div class="bg-white/25 flex py-[10px] px-[20px] rounded-4xl gap-12 shadow-md">
      <span
        v-for="(item, index) in navItems"
        :key="index"
        class="text-white opacity-100 cursor-pointer font-bold text-lg hover:text-moisten-orange"
        >{{ item }}</span
      >
    </div>
  </nav>

  <nav @click="toggleMenu" class="fixed block md:hidden top-5 right-5 text-white z-50">
    <i
      class="text-3xl cursor-pointer"
      :class="oepnMenu ? 'ri-close-line text-moisten-text' : 'ri-menu-line'"
    ></i>
  </nav>
  <SmallMenu v-if="oepnMenu" :navItems="navItems" />
</template>
