<script setup>
import { onMounted } from 'vue'
import BottomOne from '@/components/BottomOne.vue'
import ScrollReveal from 'scrollreveal'

const scrollRevealOption = {
  distance: '50px',
  origin: 'bottom',
  duration: 1000,
}

onMounted(() => {
  ScrollReveal().reveal('.introduce-img', {
    ...scrollRevealOption,
  })

  ScrollReveal().reveal('.introduce-content', {
    ...scrollRevealOption,
    origin: 'right',
    delay: 500,
  })
})
</script>

<template>
  <div class="bg-moisten-light-green relative wave-bg px-4 xl:px-0">
    <div class="max-w-7xl mx-auto pt-[45px] pb-[45px] xl:pt-[110px] xl:pb-[120px] relative">
      <div
        class="hidden md:block absolute top-[110px] right-0 w-[155px] h-[155px] border border-t-white border-r-white border-b-0 border-l-0"
      ></div>
      <div
        class="hidden md:block absolute bottom-[220px] -right-[110px] text-4xl font-bold text-white opacity-20 rotate-90"
      >
        ENJOY LIFES
      </div>

      <h2 class="moisten-text text-[26px] xl:text-4xl font-bold text-center xl:text-left">
        從餐桌出發，回到生活
      </h2>

      <div
        class="flex flex-col xl:flex-row items-center justify-between gap-5 xl:gap-[128px] mt-10 xl:mt-[120px]"
      >
        <div
          class="introduce-img max-w-[630px] max-h-[478px] flex items-center justify-center rounded-xl overflow-hidden"
        >
          <img
            class="object-cover"
            src="https://images.unsplash.com/photo-1632657583981-938d58b18b09?q=80&w=774&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
            alt=""
          />
        </div>

        <div class="introduce-content flex-1 flex items-start flex-col gap-[35px] xl:self-end">
          <div class="text-white text-xl">
            <div>我們從一間小小的公寓廚房出發，</div>
            <div>邀請你透過味覺與感官，</div>
            <div>重新看見生活裡那些被忽略的關係與議題。</div>
            <div class="pt-[28px]">關於土地、飲食、身體，與我們自己。</div>
          </div>

          <div
            class="h-[105px] border border-t-0 border-r-0 border-b-0 border-l-white ml-4 xl:ml-0"
          ></div>

          <BottomOne />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.wave-bg::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('../assets/img/wave.svg');
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

@media (min-width: 1921px) {
  .wave-bg::before {
    background-image: url('../assets/img/wave01.svg');
    background-size: cover;
  }
}

@media (max-width: 640px) {
  .wave-bg::before {
    top: unset;
    bottom: 0px;
    left: 0px;
    background-image: url('../assets/img/wave-small.svg');
    background-size: contain;
    background-repeat: no-repeat;
    background-position: bottom;
  }
}
</style>
