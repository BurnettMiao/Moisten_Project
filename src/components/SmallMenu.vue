<script setup>
const props = defineProps({
  navItems: {
    type: Array,
    required: true,
  },
})

const emit = defineEmits(['scroll-to'])

const handleClick = (targetId) => {
  emit('scroll-to', targetId)
}
</script>
<template>
  <div
    class="fixed block md:hidden bg-moisten-white px-4 top-0 left-0 w-full h-screen pt-[90px] z-40"
  >
    <div v-for="(item, itemIndex) in props.navItems" :key="itemIndex">
      <div
        @click="handleClick(item.target)"
        class="py-3 text-xl font-bold text-center cursor-pointer hover:text-moisten-orange"
      >
        {{ item.text }}
      </div>
      <div
        v-if="itemIndex !== props.navItems.length - 1"
        class="w-full h-[1px] bg-moisten-text opacity-30"
      ></div>
    </div>
  </div>
</template>
