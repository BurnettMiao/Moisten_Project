<script setup>
import { ref } from 'vue'

const navItems = ref(['關於我們', '我們目標', '活動紀錄', '商店', '常見問題', '聯絡我們'])
</script>

<template>
  <nav class="w-full flex items-center justify-center gap-12 py-[20px] fixed">
    <div class="bg-white/25 flex py-[10px] px-[20px] rounded-4xl gap-12">
      <span
        v-for="(item, index) in navItems"
        :key="index"
        class="text-white opacity-100 cursor-pointer font-bold hover:text-moisten-bg-orange"
        >{{ item }}</span
      >
    </div>
  </nav>
</template>
