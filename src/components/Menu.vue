<script setup>

const props = defineProps({
  unitItems: Object,
  isActive: Boolean
})

const emit = defineEmits(['changeMenuStatus'])
</script>

<template>
  <div
  class="menu"
  :class="{ active: isActive }"
  >
    <a
    class="close-btn"
    href="javascript:;"
    @click="$emit('changeMenuStatus')"
    >
    </a>
    <div class="unit-wrap">
      <a
      class="links"
      :href="item.href"
      :class="{disable: item.isDisable}"
      v-for="item in unitItems"
      :key="item.name"
      >
      {{ item.name }}
      </a>
    </div>
  </div>
</template>

<style lang="sass">
@import './../assets/sass/mixins'

.menu
  position: fixed
  z-index: 9
  right: 0
  top: 0
  bottom: 0
  width: 75%
  max-width: 800px
  background-color: rgba(#fff, .1)
  backdrop-filter: blur(20px)
  padding: 100px 60px
  opacity: 0
  transform: translateX(100%)
  transition: $transition
  +rwdmax(767)
    width: 80%
    padding: 100px 30px
  &.active
    opacity: 1
    transform: translateX(0)
  .close-btn
    position: absolute
    top: 30px
    right: 30px
    width: 30px
    height: 30px
    &::before, &::after
      width: 25px
      height: 2px
      background-color: #fff
      +posCenter
      +pseudo
    &::before
      transform: translate(-50%, -50%) rotate(45deg)
    &::after
      transform: translate(-50%, -50%) rotate(-45deg)
  .unit-wrap
    width: 100%
    display: flex
    flex-direction: column
    align-items: flex-start
    a
      margin: 15px 0
</style>