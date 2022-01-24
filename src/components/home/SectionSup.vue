<script setup>
import { reactive } from 'vue'

import supporter01 from './../../assets/image/home/supporter-01.png'
import supporter02 from './../../assets/image/home/supporter-02.png'
import supporter03 from './../../assets/image/home/supporter-03.png'
import supporter04 from './../../assets/image/home/supporter-04.png'

const supBlockData = reactive([
  {
    id: '01',
    img: supporter01
  },
  {
    id: '02',
    img: supporter02
  },
  {
    id: '03',
    img: supporter03
  },
  {
    id: '04',
    img: supporter04
  }
])
</script>

<template>
  <section class="sup-block space-lr">
    <div class="block-content maxw-1200">
      <div class="term" data-aos="fade">STRATEGIC SUPPORTER</div>
      <div class="content-item" data-aos="fade-up">
        <div
        class="each-sup"
        v-for="item in supBlockData"
        :key="item.id"
        >
          <img :src="item.img">
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