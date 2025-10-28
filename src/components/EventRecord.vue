<script setup>
import { ref, onMounted } from 'vue'
import SectionTitle from '@/components/utility/SectionTitle.vue'
import EventCard from '@/components/utility/EventCard.vue'
import ScrollReveal from 'scrollreveal'

// Event Record Section 請在此處加入圖片連結文字 ↓↓↓↓↓
const eventCardsInfo = ref({
  title: '活動紀錄',
  cardContent: [
    {
      img: 'https://frauaustee.co.uk/moisten_images/01/01.jpg',
      year: '2018',
      lable: '北市社宅青創團隊',
      title: '野餐Pizza',
    },
    {
      img: 'https://frauaustee.co.uk/moisten_images/02/01.jpg',
      year: '2021',
      lable: '高齡者陪伴',
      title: '冬至湯圓',
    },
    {
      img: 'https://frauaustee.co.uk/moisten_images/03/01.jpg',
      year: '2021',
      lable: '社宅住戶',
      title: '新疆菜',
    },
    {
      img: 'https://frauaustee.co.uk/moisten_images/04/01.jpg',
      year: '2025',
      lable: '風格市集',
      title: '復古主題',
    },
  ],
})
// Event Record Section 請在此處加入圖片連結及文字 ↑↑↑↑↑

const eventCardRef = ref(null)

const handlePrevSlide = () => {
  // console.log('handlePrevSlide clicked')
  // console.log('eventCardRef.value:', eventCardRef.value)
  if (eventCardRef.value) {
    // console.log('calling slidePrev')
    eventCardRef.value.slidePrev()
  } else {
    console.log('eventCardRef.value is null')
  }
}

const handleNextSlide = () => {
  // console.log('handleNextSlide clicked')
  // console.log('eventCardRef.value:', eventCardRef.value)
  if (eventCardRef.value) {
    // console.log('calling slideNext')
    eventCardRef.value.slideNext()
  } else {
    console.log('eventCardRef.value is null')
  }
}

const scrollRevealOption = {
  distance: '50px',
  origin: 'bottom',
  duration: 1000,
}

onMounted(() => {
  ScrollReveal().reveal('.event-card', {
    ...scrollRevealOption,
    delay: 500,
  })
})
</script>

<template>
  <div id="event-section" class="bg-moisten-light-green/50 scroll-mt-[100px]">
    <div class="max-w-7xl mx-auto pt-[55px] pb-[55px] xl:pt-[65px] xl:pb-[85px] px-4 xl:px-0">
      <div class="w-full flex items-center justify-between">
        <SectionTitle>{{ eventCardsInfo.title }}</SectionTitle>
        <div class="hidden lg:flex items-center justify-center gap-[17px]">
          <div
            @click="handlePrevSlide"
            class="w-[30px] h-[30px] border border-moisten-text rounded-full cursor-pointer flex items-center justify-center text-xl group hover:border-moisten-orange hover:bg-moisten-orange duration-300"
          >
            <i class="ri-arrow-left-line group-hover:text-white"></i>
          </div>
          <div
            @click="handleNextSlide"
            class="w-[30px] h-[30px] border border-moisten-text rounded-full cursor-pointer flex items-center justify-center text-xl group hover:border-moisten-orange hover:bg-moisten-orange duration-300"
          >
            <i class="ri-arrow-right-line group-hover:text-white"></i>
          </div>
        </div>
      </div>

      <EventCard
        class="event-card"
        ref="eventCardRef"
        :eventCardsInfo="eventCardsInfo.cardContent"
      />
    </div>
  </div>
</template>
