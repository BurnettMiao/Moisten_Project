<script setup>
import { ref } from 'vue'
import SectionTitle from '@/components/SectionTitle.vue'
import EventCard from '@/components/EventCard.vue'

const eventCardsInfo = ref([
  {
    img: 'https://images.unsplash.com/photo-1516382461343-35e1ba016e01?q=80&w=1548&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    year: '2019',
    title: '風格市集擺攤',
    lable: '二手市集、、跳蚤市場',
  },
  {
    img: 'https://images.unsplash.com/photo-1556442281-77c90134c61f?q=80&w=1740&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    year: '2021',
    title: '蜜桃釀酒',
    lable: '節氣活動',
  },
  {
    img: 'https://images.unsplash.com/photo-1592417817038-d13fd7342605?ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&q=80&w=1740',
    year: '2025',
    title: 'Moisten',
    lable: '浸潤茶葉佐餐',
  },
  {
    img: 'https://images.unsplash.com/photo-1556442281-77c90134c61f?q=80&w=1740&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    year: '2021',
    title: '蜜桃釀酒',
    lable: '節氣活動',
  },
])
</script>

<template>
  <div class="bg-moisten-light-green/50">
    <div class="max-w-7xl mx-auto pt-[55px] pb-[55px] xl:pt-[65px] xl:pb-[85px] px-4 xl:px-0">
      <div class="w-full flex items-center justify-between">
        <SectionTitle>活動紀錄</SectionTitle>
        <div class="flex items-center justify-center gap-[17px]">
          <div
            class="w-[30px] h-[30px] border border-moisten-text rounded-full cursor-pointer flex items-center justify-center text-xl group hover:border-moisten-orange hover:bg-moisten-orange duration-300"
          >
            <i class="ri-arrow-left-line group-hover:text-white"></i>
          </div>
          <div
            class="w-[30px] h-[30px] border border-moisten-text rounded-full cursor-pointer flex items-center justify-center text-xl group hover:border-moisten-orange hover:bg-moisten-orange duration-300"
          >
            <i class="ri-arrow-right-line group-hover:text-white"></i>
          </div>
        </div>
      </div>

      <EventCard :eventCardsInfo="eventCardsInfo" />
    </div>
  </div>
</template>
