<script setup>
import { onMounted } from 'vue'
import ScrollReveal from 'scrollreveal'

import SectionTitle from '@/components/SectionTitle.vue'

const ourGoalsContent = [{}]

const scrollRevealOption = {
  distance: '50px',
  origin: 'bottom',
  duration: 1000,
}

onMounted(() => {
  ScrollReveal().reveal('.goals-one-card', {
    ...scrollRevealOption,
    origin: 'left',
  })
  ScrollReveal().reveal('.goals-one-pic', {
    ...scrollRevealOption,
    origin: 'right',
    delay: 500,
  })

  ScrollReveal().reveal('.goals-two-pic', {
    ...scrollRevealOption,
    origin: 'left',
    delay: 1000,
  })
  ScrollReveal().reveal('.goals-two-card', {
    ...scrollRevealOption,
    origin: 'bottom',
    delay: 1500,
  })

  // ScrollReveal().reveal('.goals-three-card', {
  //   ...scrollRevealOption,
  //   origin: 'right',
  //   delay: 1500,
  // })
  ScrollReveal().reveal('.goals-three-pic', {
    ...scrollRevealOption,
    origin: 'bottom',
    delay: 1800,
  })
})
</script>

<template>
  <div class="bg-moisten-white">
    <div class="max-w-7xl mx-auto pt-[55px] pb-[75px] xl:pt-[75px] xl:pb-[110px] px-4 xl:px-0">
      <SectionTitle>我們目標</SectionTitle>

      <div
        class="goals-one-card mt-10 xl:mt-15 flex flex-col items-center justify-around gap-13 xl:gap-20 max-w-[640px] xl:max-w-full mx-auto"
      >
        <div class="flex flex-col-reverse xl:flex-row items-center justify-center">
          <div class="relative left-0 xl:left-[18px] w-full xl:max-w-[355px]">
            <div class="relative w-full xl:w-[380px] bg-moisten-white z-10">
              <div class="px-[15px] xl:px-[32px] py-[30px] flex flex-col gap-4">
                <div>
                  <div class="text-[24px] xl:text-[26px] text-moisten-green font-bold">
                    關注在地社會議題
                  </div>
                  <div class="text-lg">小資廚房進化中...</div>
                </div>
                <div class="w-full h-[1px] bg-moisten-text"></div>
                <div class="text-lg flex flex-col gap-5">
                  <div>創辦人主修建築，曾於建築師事務所及銀行擔任建築管理相關工作。</div>
                  <div>
                    因察覺都市冷漠問題及台灣社會住宅發展的遲滯，於2018至2019年間，投入社會議題的提案與行動實驗。
                  </div>
                  <div>相關後續於2023年完成學術論文撰寫，現階段專注回歸料理領域。</div>
                </div>
              </div>
            </div>

            <div
              class="absolute w-[355px] h-[185px] -bottom-[18px] -left-[18px] bg-moisten-light-green z-0"
            ></div>
          </div>

          <div
            class="goals-one-pic max-w-[630px] xl:max-w-[925px] max-h-[485px] overflow-hidden rounded-2xl relative"
          >
            <img
              class="w-full h-full object-cover object-center"
              src="https://images.unsplash.com/photo-1472926373053-51b220987527?q=80&w=1738&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
              alt=""
            />
          </div>
        </div>

        <div class="flex items-center justify-center flex-col xl:flex-row">
          <div
            class="goals-two-pic max-w-[630px] xl:max-w-[925px] max-h-[485px] overflow-hidden rounded-2xl relative"
          >
            <img
              class="w-full h-full object-cover object-center"
              src="https://images.unsplash.com/photo-1624893464636-c122891445c6?q=80&w=1740&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
              alt=""
            />
          </div>

          <div class="goals-two-card relative right-0 xl:right-[50px] w-full xl:max-w-[355px]">
            <div
              class="relative w-full xl:w-[380px] bg-moisten-white z-10 -right-0 xl:-right-[8px]"
            >
              <div class="px-[15px] xl:px-[32px] py-[30px] flex flex-col gap-4">
                <div>
                  <div class="text-[24px] xl:text-[26px] text-moisten-green font-bold">
                    符合道德的材料
                  </div>
                  <div class="text-lg">追尋日本宇治茶的來源，建立產地來源的新關係。</div>
                </div>
                <div class="w-full h-[1px] bg-moisten-text"></div>
                <div class="text-lg flex flex-col gap-5">
                  <div>2012年負責人在日本和束町，與在地茶農接觸後，注意到茶源鄉的正名運動。</div>
                  <div>我們決定不只關心味道，並開始注意食材的生命歷程。</div>
                  <div>道德的材料，不僅是味道上的享受，也是尊重土地、農人與自然的選擇。</div>
                </div>
              </div>
            </div>

            <div
              class="absolute w-[355px] h-[185px] -bottom-[18px] -right-[18px] xl:-right-[50px] bg-moisten-light-green z-0"
            ></div>
          </div>
        </div>

        <div class="flex items-center justify-center flex-col-reverse xl:flex-row">
          <div class="goals-three-card relative xl-left-0 xl:left-[18px] w-full xl:max-w-[355px]">
            <div class="relative w-full xl:w-[380px] bg-moisten-white z-10">
              <div class="px-[15px] xl:px-[32px] py-[30px] flex flex-col gap-4">
                <div>
                  <div class="text-[24px] xl:text-[26px] text-moisten-green font-bold">
                    環境永續
                  </div>
                  <div class="text-lg">除了活動設計，我們正在學習更永續的環境議題。</div>
                </div>
                <div class="w-full h-[1px] bg-moisten-text"></div>
                <div class="text-lg flex flex-col gap-5">
                  <div>
                    廚房透過活動設計與實驗，以及日常與外界的交流，我們從餐桌出發，探索更永續的循環方式。
                  </div>
                  <div>
                    2025年起，我們將目光重新聚焦於台灣茶，讓佐餐飲品的選擇更加低碳，實踐在地永續。
                  </div>
                </div>
              </div>
            </div>

            <div
              class="absolute w-[355px] h-[185px] -bottom-[18px] -left-[18px] bg-moisten-light-green z-0"
            ></div>
          </div>

          <div
            class="goals-three-pic max-w-[630px] xl:max-w-[925px] max-h-[485px] overflow-hidden rounded-2xl relative"
          >
            <img
              class="w-full h-full object-cover object-center"
              src="https://images.unsplash.com/photo-1542601906990-b4d3fb778b09?q=80&w=2026&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
              alt=""
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
