<script setup></script>

<template>
  <div class="title-dot relative text-[26px] xl:text-4xl font-bold pl-[30px]">
    <slot></slot>
  </div>
</template>

<style scoped>
.title-dot::before {
  content: '';
  position: absolute;
  display: block;
  top: 3px;
  left: 0;
  height: 15px;
  width: 15px;
  background-color: var(--color-moisten-orange);
}

@media screen and (max-width: 1280px) {
  .title-dot {
    font-family: 'Libre Baskerville', serif;
  }

  .title-dot::before {
    top: 7px;
  }
}
</style>
