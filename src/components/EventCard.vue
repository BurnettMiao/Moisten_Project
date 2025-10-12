<script setup>
const props = defineProps({
  eventCardsInfo: {
    type: Array,
    require: true,
  },
})
</script>
<template>
  <div class="mt-[55px] flex items-center justify-between">
    <div
      v-for="(item, itenIndex) in props.eventCardsInfo"
      class="max-w-[410px] rounded-lg overflow-hidden cursor-pointer group"
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
    </div>
  </div>
</template>
