<script setup>
import { ref } from 'vue'

const navItems = ref(['關於我們', '我們目標', '活動紀錄', '商店', '常見問題', '聯絡我們'])
</script>

<template>
  <nav class="flex items-center justify-between">
    <span v-for="(item, index) in navItems" :key="index">{{ item }}</span>
  </nav>
</template>
