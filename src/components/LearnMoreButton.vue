<script setup>
// 滾動到指定 section
const scrollToSection = () => {
  const element = document.getElementById('goals-section')

  if (element) {
    element.scrollIntoView({
      behavior: 'smooth',
      block: 'start',
    })
  }
}
</script>
<template>
  <div
    @click="scrollToSection"
    class="inline-block px-[15px] py-[16px] border border-white rounded-xl text-white text-xl cursor-pointer duration-300 hover:bg-moisten-orange hover:border-moisten-orange"
  >
    LEARN MORE
  </div>
</template>
