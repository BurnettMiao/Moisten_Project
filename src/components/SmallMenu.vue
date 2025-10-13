<script setup>
const props = defineProps({
  navItems: {
    type: Array,
    required: true,
  },
})
</script>
<template>
  <div
    class="fixed block md:hidden bg-moisten-white px-4 top-0 left-0 w-full h-screen pt-[90px] z-40"
  >
    <div v-for="(item, itemIndex) in props.navItems" :key="itemIndex">
      <div class="py-3 text-lg font-bold text-center cursor-pointer hover:text-moisten-orange">
        {{ item }}
      </div>
      <div
        v-if="itemIndex !== props.navItems.length - 1"
        class="w-full h-[1px] bg-moisten-text opacity-30"
      ></div>
    </div>
  </div>
</template>
