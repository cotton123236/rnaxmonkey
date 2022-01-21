<script setup>
import { reactive } from 'vue'

const supBlockData = reactive([
  {
    id: '01',
    img: 'supporter-01.png'
  },
  {
    id: '02',
    img: 'supporter-02.png'
  },
  {
    id: '03',
    img: 'supporter-03.png'
  },
  {
    id: '04',
    img: 'supporter-04.png'
  }
])
</script>

<template>
  <section class="sup-block space-lr">
    <div class="block-content maxw-1200">
      <div class="term">STRATEGIC SUPPORTER</div>
      <div class="content-item">
        <div
        class="each-sup"
        v-for="item in supBlockData"
        :key="item.id"
        >
          <img :src="`/src/assets/image/home/${item.img}`">
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="sass" scoped>
@import './../../assets/sass/mixins'

.sup-block
  position: relative
  padding-bottom: 60px
  .content-item
    display: flex
    flex-wrap: wrap
    justify-content: center
    gap: 12px
    margin-top: 50px
    +rwdmax(767)
      gap: 10px
      margin-top: 40px
  .each-sup
    width: calc(25% - 9px)
    max-width: 290px
    border: 1px solid rgba(255, 255, 255, 0.3)
    border-radius: 12px
    padding: 10px 20px
    transition: $transition
    +flex
    +rwdmax(900)
      width: calc(50% - 6px)
    +rwdmax(767)
      width: calc(50% - 5px)
    &:hover
      transform: translateY(-5px)
</style>