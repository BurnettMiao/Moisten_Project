<script setup>
import { ref } from 'vue'
const props = defineProps({
  eventCardsInfo: {
    type: Array,
    required: true,
  },
})

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue'
// import required modules
import { Pagination } from 'swiper/modules'
// Import Swiper styles
import 'swiper/css'
import 'swiper/css/pagination'

const modules = [Pagination]
const swiperRef = ref(null)
const swiperInstance = ref(null)

const onSwiper = (swiper) => {
  console.log('onSwiper called:', swiper)
  swiperInstance.value = swiper
}

// 暴露方法給父組件
defineExpose({
  slidePrev: () => {
    console.log('slidePrev called, swiperInstance:', swiperInstance.value)
    if (swiperInstance.value) {
      swiperInstance.value.slidePrev()
    } else {
      console.log('swiperInstance is null')
    }
  },
  slideNext: () => {
    console.log('slideNext called, swiperInstance:', swiperInstance.value)
    if (swiperInstance.value) {
      swiperInstance.value.slideNext()
    } else {
      console.log('swiperInstance is null')
    }
  },
})
</script>
<template>
  <swiper
    ref="swiperRef"
    @swiper="onSwiper"
    :loop="true"
    :slides-per-view="'auto'"
    :space-between="20"
    :modules="modules"
    class="mt-[30px] xl:mt-[55px]"
  >
    <swiper-slide
      v-for="(item, itenIndex) in props.eventCardsInfo"
      class="max-w-[320px] lg:max-w-[410px] rounded-lg overflow-hidden cursor-pointer group"
      :key="itenIndex"
    >
      <div class="w-full h-[360px] overflow-hidden">
        <img
          class="w-full h-full object-cover object-center transition-transform duration-300 group-hover:scale-120"
          :src="item.img"
          alt=""
        />
      </div>

      <div class="bg-moisten-white px-[15px] py-[25px] flex items-end justify-between">
        <div
          class="px-[7px] py-[5px] text-lg text-white font-weight font-bold bg-moisten-green rounded-lg text-[20px]"
        >
          {{ item.year }}
        </div>

        <div class="flex flex-col items-end">
          <div class="text-[14px] text-moisten-text-gary">{{ item.lable }}</div>
          <div class="text-[26px] font-bold text-moisten-text">{{ item.title }}</div>
        </div>
      </div>
    </swiper-slide>
  </swiper>
</template>
