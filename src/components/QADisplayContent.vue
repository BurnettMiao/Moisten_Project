<script setup>
import { ref, onMounted, watch } from 'vue'
import ScrollReveal from 'scrollreveal'
const props = defineProps({
  qaInfo: {
    type: Array,
    require: true,
  },
})

const isOpen = ref([])

const initIsOpen = () => {
  isOpen.value = props.qaInfo.map((_, idx) => idx === 0)
}

const toggleOpen = (index) => {
  isOpen.value[index] = !isOpen.value[index]
}

const scrollRevealOption = {
  distance: '50px',
  origin: 'bottom',
  duration: 1000,
}

onMounted(() => {
  initIsOpen()

  ScrollReveal().reveal('.qa-1', {
    ...scrollRevealOption,
    origin: 'right',
    delay: 500,
  })
  ScrollReveal().reveal('.qa-2', {
    ...scrollRevealOption,
    origin: 'right',
    delay: 1000,
  })
  ScrollReveal().reveal('.qa-3', {
    ...scrollRevealOption,
    origin: 'right',
    delay: 1500,
  })
})

watch(() => props.qaInfo, initIsOpen, { immediate: true })
</script>
<template>
  <div
    v-for="(item, itemIndex) in props.qaInfo"
    class="w-full px-[25px] py-[20px] shadow-md flex flex-col gap-2"
    :class="`qa-${itemIndex + 1}`"
    :key="itemIndex"
  >
    <div
      @click="toggleOpen(itemIndex)"
      class="flex items-start justify-between border border-b-moisten-text border-t-0 border-r-0 border-l-0 pb-1 cursor-pointer"
    >
      <div class="text-xl text-moisten-text font-bold">{{ item.title }}</div>
      <i
        class="text-3xl font-bold text-moisten-text"
        :class="isOpen[itemIndex] ? 'ri-arrow-up-s-line' : 'ri-arrow-down-s-line'"
      ></i>
    </div>

    <Transition name="qa-fade">
      <div v-show="isOpen[itemIndex]" class="text-lg pt-1 duration-300">
        {{ item.content }}
      </div>
    </Transition>
  </div>
</template>
<style scoped>
.qa-fade-enter-active,
.qa-fade-leave-active {
  transition:
    max-height 0.2s cubic-bezier(0.4, 0, 0.2, 1),
    opacity 0.3s;
  overflow: hidden;
}
.qa-fade-enter-from,
.qa-fade-leave-to {
  max-height: 0;
  opacity: 0;
}
.qa-fade-enter-to,
.qa-fade-leave-from {
  max-height: 500px;
  opacity: 1;
}
</style>
