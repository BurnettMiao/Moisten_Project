<script setup>
import { ref } from 'vue'
import SectionTitle from '@/components/utility/SectionTitle.vue'
import QADisplayContent from '@/components/utility/QADisplayContent.vue'
// 請在此處加入文字 ↓↓↓↓↓
const qaInfo = ref({
  title: '常見問題',
  content: [
    {
      title: '製作RWD響應式網站需要準備些什麼？',
      content:
        '其實它與一般PC版網站製作的方式一樣，Quarter的專業設計團隊，會引導並協助您做架構內容的規劃，您只需要準備製作相關的圖片，及內容文字給我們即可。',
    },
    {
      title:
        '這些模板通常由網站開發公司或平台提供，客戶可以根據自己的需要對其進行一定程度的修改，如更改內容、圖片、字體、顏色等，以達到個性化需求。',
      content:
        '第二段文字，其實它與一般PC版網站製作的方式一樣，Quarter的專業設計團隊，會引導並協助您做架構內容的規劃，您只需要準備製作相關的圖片，及內容文字給我們即可。',
    },
    {
      title: '「設計形象風格」則是指網站的整體風格和外觀，例如顏色、字體、版面設計、圖片和圖形等。',
      content:
        '第三段文字，其實它與一般PC版網站製作的方式一樣，Quarter的專業設計團隊，會引導並協助您做架構內容的規劃，您只需要準備製作相關的圖片，及內容文字給我們即可。',
    },
  ],
})
// 請在此處加入文字 ↑↑↑↑↑
</script>

<template>
  <div
    id="qa-section"
    class="bg-moisten-white max-w-[1064px] mx-auto pt-0 xl:pt-[55px] pb-[55px] xl:pb-[110px] flex flex-col xl:flex-row items-stretch justify-between gap-0 xl:gap-10 px-4 xl:px-0 scroll-mt-[100px]"
  >
    <div class="h-auto flex flex-col items-start xl:items-end justify-between gap-5">
      <SectionTitle>{{ qaInfo.title }}</SectionTitle>
      <div
        class="flex-1 h-[300px] w-[12.5px] border border-moisten-text border-l-[1px] border-t-0 border-r-0 border-b-0"
      ></div>
      <div class="hidden xl:block w-[25px] h-[25px] bg-moisten-orange"></div>
    </div>

    <div class="flex-1 flex flex-col gap-3">
      <QADisplayContent :qaInfo="qaInfo.content" />
    </div>
  </div>
</template>
