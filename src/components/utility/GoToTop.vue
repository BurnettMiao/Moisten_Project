<script setup>
const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth',
  })
}
</script>

<template>
  <div
    @click="scrollToTop"
    class="fixed bottom-8 right-8 sm:bottom-10 sm:right-10 w-10 h-10 rounded-full bg-moisten-orange flex items-center justify-center shadow-lg cursor-pointer pb-1 z-40"
  >
    <i class="ri-arrow-up-s-line text-white text-4xl"></i>
  </div>
</template>
