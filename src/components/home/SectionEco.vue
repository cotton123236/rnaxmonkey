<script setup>
import { reactive } from 'vue'

import eco01 from './../../assets/image/home/eco-01.png'
import eco02 from './../../assets/image/home/eco-02.png'
import eco03 from './../../assets/image/home/eco-03.png'
import eco04 from './../../assets/image/home/eco-04.png'

const ecoBlockData = reactive([
  {
    id: '01',
    img: eco01,
    title: 'In-game Currency'
  },
  {
    id: '02',
    img: eco02,
    title: 'Governance'
  },
  {
    id: '03',
    img: eco03,
    title: 'Staking'
  },
  {
    id: '04',
    img: eco04,
    title: 'Play 2 Earn'
  }
])
</script>

<template>
  <section class="eco-block space-lr">
    <div class="block-content maxw-1200">
      <div class="term">TOKEN ECONOMICS</div>
      <div class="content-item">
        <div
        class="each-eco"
        v-for="item in ecoBlockData"
        :key="item.id"
        >
          <div class="inner">
            <div
            class="icon"
            :style="{ backgroundImage: `url(${item.img})` }"
            >
            </div>
            <div class="title">{{ item.title }}</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="sass" scoped>
@import './../../assets/sass/mixins'

.eco-block
  position: relative
  padding-top: 60px
  padding-bottom: 60px
  .content-item
    display: flex
    flex-wrap: wrap
    justify-content: center
    gap: 30px
    margin-top: 70px
    +rwdmax(1024)
      margin-top: 50px
    +rwdmax(767)
      gap: 10px
      margin-top: 40px
  .each-eco
    width: calc(25% - 22.5px)
    max-width: 280px
    border: 1px solid rgba(255, 255, 255, 0.3)
    border-radius: 12px
    padding: 60px 40px
    transition: $transition
    +rwdmax(900)
      width: calc(50% - 15px)
    +rwdmax(767)
      width: calc(50% - 5px)
      padding: 30px 20px
    &:hover
      transform: translateY(-5px)
      border-color: $pink-light
      .title
        color: $pink-light
    .inner
      width: 100%
      max-width: 175px
      margin: auto
    .icon
      width: 100%
      padding-bottom: 100%
      background-size: cover
      background-position: center
      background-repeat: no-repeat
    .title
      font-size: px(18)
      font-weight: 600
      line-height: 1.3
      text-align: center
      margin-top: 30px
      transition: $transition
      +rwdmax(767)
        font-size: px(16)
</style>