<script setup>
import { reactive } from 'vue'

import intro01 from './../../assets/image/home/intro-01.png'
import intro02 from './../../assets/image/home/intro-02.png'
import intro03 from './../../assets/image/home/intro-03.png'

const homeBlockData = reactive({
  title: 'RNA x MONKEY GAME ON BLOCKCHAIN',
  img: [
    intro01,
    intro02,
    intro03
  ]
})
</script>

<template>
  <section class="home-block space-lr">
    <div class="block-content maxw-1200">
      <div class="content-left">
        <div class="title">{{ homeBlockData.title }}</div>
        <div class="btn-wrap">
          <a class="pill-btn fill" href="javascript:;" target="_blank"><span>Buy $RMK</span></a>
          <a class="pill-btn" href="javascript:;" targt="_blank"><span>Getting Started</span></a>
        </div>
      </div>
      <div class="content-right">
        <div class="inner-wrap">
          <div class="image-wrap">
            <img
            v-for="item in homeBlockData.img"
            :key="item"
            :src="item"
            >
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="sass" scoped>
@import './../../assets/sass/mixins'

.home-block
  position: relative
  padding-top: 50px
  padding-bottom: 120px
  overflow: hidden
  +rwdmax(767)
    padding-top: 40px
    padding-bottom: 80px
  .block-content
    position: relative
    display: flex
    align-items: center
    +rwdmax(1024)
      flex-direction: column-reverse
  .content-left
    position: relative
    z-index: 2
    max-width: 500px
    +rwdmax(1024)
      width: 100%
      max-width: none
    .title
      font-size: px(58)
      font-weight: 700
      line-height: 1.2
      +rwdmax(1024)
        text-align: center
        font-size: px(42)
      +rwdmax(767)
        font-size: px(34)
    .btn-wrap
      display: flex
      align-items: center
      margin-top: 48px
      +rwdmax(1024)
        justify-content: center
        font-size: px(30)
    .pill-btn
      &:not(:last-child)
        margin-right: 15px
  .content-right
    position: relative
    flex: 1
    height: 450px
    +rwdmax(1024)
      width: 100%
      flex: none
      height: auto
    .inner-wrap
      position: absolute
      top: 0
      right: 0
      width: 150%
      max-width: 770px
      +rwdmax(1024)
        position: relative
        right: auto
        width: 100%
        margin: auto
    .image-wrap
      width: 100%
      padding-bottom: 58.5%
      +rwdmax(767)
        padding-bottom: 62%
    img
      position: absolute
      &:nth-child(2)
        z-index: 2
        width: 35%
        left: 50%
        transform: translateX(-50%)
        max-width: 265px
      &:nth-child(1)
        z-index: 1
        width: 40%
        max-width: 285px
        bottom: 0
        left: 0
      &:nth-child(3)
        z-index: 1
        width: 42%
        max-width: 300px
        bottom: 0
        right: 0
</style>