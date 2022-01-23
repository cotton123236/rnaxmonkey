<script setup>
import { ref, reactive } from 'vue'
import { Autoplay } from 'swiper'
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'

import charaImg01 from './../../assets/image/home/chara-01.png'
import charaImg02 from './../../assets/image/home/chara-02.png'
import charaImg03 from './../../assets/image/home/chara-03.png'
import charaIcon01 from './../../assets/image/home/chara-ele-01.png'
import charaIcon02 from './../../assets/image/home/chara-ele-03.png'
import charaIcon03 from './../../assets/image/home/chara-ele-03.png'
import chara01_item01 from './../../assets/image/home/chara-01-item-01.png'
import chara01_item02 from './../../assets/image/home/chara-01-item-02.png'
import chara01_item03 from './../../assets/image/home/chara-01-item-03.png'
import chara01_item04 from './../../assets/image/home/chara-01-item-04.png'
import chara02_item01 from './../../assets/image/home/chara-02-item-01.png'
import chara02_item02 from './../../assets/image/home/chara-02-item-02.png'
import chara02_item03 from './../../assets/image/home/chara-02-item-03.png'
import chara02_item04 from './../../assets/image/home/chara-02-item-04.png'
import chara03_item01 from './../../assets/image/home/chara-03-item-01.png'
import chara03_item02 from './../../assets/image/home/chara-03-item-02.png'
import chara03_item03 from './../../assets/image/home/chara-03-item-03.png'
import chara03_item04 from './../../assets/image/home/chara-03-item-04.png'

const charaSwiper = ref(null)
const charaBlockData = reactive([
  {
    name: 'Goku',
    img: charaImg01,
    icon: charaIcon01,
    ele: 'Light',
    item: [
      chara01_item01,
      chara01_item02,
      chara01_item03,
      chara01_item04
    ]
  },
  {
    name: 'Quinn',
    img: charaImg02,
    icon: charaIcon02,
    ele: 'Fire',
    item: [
      chara02_item01,
      chara02_item02,
      chara02_item03,
      chara02_item04
    ]
  },
  {
    name: 'Singed',
    img: charaImg03,
    icon: charaIcon03,
    ele: 'Earth',
    item: [
      chara03_item01,
      chara03_item02,
      chara03_item03,
      chara03_item04
    ]
  }
])

const onSwiperInit = (swiper) => {
  charaSwiper.value = swiper
}

const slidePrev = () => {
  console.log(charaSwiper.value);
  charaSwiper.value.slidePrev()
}

const slideNext = () => {
  console.log(charaSwiper.value);
  charaSwiper.value.slideNext()
}

</script>

<template>
  <section class="chara-block space-lr">
    <div class="block-content maxw-1200">
      <div class="term">GAME CHARACTER</div>
      <div class="content-item">
        <div class="prev-arrow-box">
          <div class="prev-arrow" @click="slidePrev">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 40 40"><path d="M20,40A20,20,0,1,1,40,20,20,20,0,0,1,20,40ZM20,2A18,18,0,1,0,38,20,18,18,0,0,0,20,2Z"/><path d="M22.5,28a1,1,0,0,1-.71-.29l-7-7a1,1,0,0,1,0-1.42l7-7a1,1,0,0,1,1.42,1.42L16.91,20l6.3,6.29a1,1,0,0,1,0,1.42A1,1,0,0,1,22.5,28Z"/></svg>
          </div>
        </div>
        <swiper
        :modules="[Autoplay]"
        :speed="600"
        :loop="true"
        :autoplay="true"
        @afterInit="onSwiperInit"
        >
          <swiper-slide
          v-for="item in charaBlockData"
          :key="item.img"
          >
            <div class="slide-inner" data-swiper-parallax-x="100%">
              <div class="photo-box">
                <div class="photo">
                  <div class="image">
                    <img :src="item.img" alt="">
                  </div>
                </div>
              </div>
              <div class="text-box">
                <div class="sub-term">
                  <div class="icon"><img :src="item.icon" alt=""></div>
                  <div class="title">
                    <div class="name">{{ item.name }}</div>
                    <div class="ele">Element: <span>{{ item.ele }}</span></div>
                  </div>
                </div>
                <div class="parts">
                  <div class="title">Body Parts</div>
                  <div class="items">
                    <div
                    class="item"
                    v-for="part in item.item"
                    :key="part"
                    >
                      <div class="inner" :style="{ backgroundImage: `url(${part})` }"></div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </swiper-slide>
        </swiper>
        <div class="next-arrow-box">
          <div class="next-arrow" @click="slideNext">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 40 40"><path d="M20,0A20,20,0,1,1,0,20,20,20,0,0,1,20,0Zm0,38A18,18,0,1,0,2,20,18,18,0,0,0,20,38Z"/><path d="M17.5,12a1,1,0,0,1,.71.29l7,7a1,1,0,0,1,0,1.42l-7,7a1,1,0,0,1-1.42-1.42L23.09,20l-6.3-6.29a1,1,0,0,1,0-1.42A1,1,0,0,1,17.5,12Z"/></svg>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="sass" scoped>
@import './../../assets/sass/mixins'

.chara-block
  position: relative
  padding-top: 60px
  padding-bottom: 60px
  .content-item
    width: 100%
    margin-top: 50px
    display: flex
    +rwdmax(767)
      margin-top: 20px
  .prev-arrow-box, .next-arrow-box
    flex: 1
    display: flex
    align-items: center
    +rwdmax(767)
      display: none
  .prev-arrow, .next-arrow
    cursor: pointer
    border-radius: 50%
    &:hover
      svg
        fill: $pink-light
    svg
      fill: $gray
      width: 40px
      transition: fill $transition
  .prev-arrow-box
    padding-right: 40px
  .next-arrow-box
    justify-content: flex-end
    padding-left: 40px
  .swiper
    max-width: 980px
  .swiper-slide
    z-index: -1
    &.swiper-slide-active, &.swiper-slide-duplicate-active
      z-index: 1
      .slide-inner
        transition: opacity .6s .3s
        opacity: 1
        .photo-box
          opacity: 1
          transform: translate(0)
        .parts
          .items
            .item
              opacity: 1
              transform: translate(0)
  .slide-inner
    display: flex
    align-items: center
    padding-top: 30px
    opacity: 0
    transition: opacity .6s
    +rwdmax(900)
      flex-direction: column
    .photo-box
      width: 35%
      max-width: 310px
      opacity: 0
      transform: translateX(50px)
      transition: $transition .4s
      +rwdmax(900)
        width: 100%
        transform: translateY(50px)
    .photo
      position: relative
      width: 100%
      padding-bottom: 133.33%
    .text-box
      flex: 1
      padding-left: 65px
      +rwdmax(900)
        width: 100%
        padding-left: 0
        padding-top: 40px
      +rwdmax(767)
        padding-top: 20px
    .sub-term
      display: flex
      align-items: center
      .icon
        width: 60px
        margin-right: 12px
      .name
        font-size: px(40)
        line-height: 1.2
        font-weight: 700
        +rwdmax(1024)
          font-size: px(34)
        +rwdmax(767)
          font-size: px(28)
      .ele
        font-size: px(14)
        font-weight: 500
        line-height: 1.5
        color: $gray
        span
          color: #fff
    .parts
      margin-top: 40px
      +rwdmax(767)
        margin-top: 20px
      .title
        font-size: px(14)
        font-weight: 500
        line-height: 1.5
      .items
        display: flex
        align-items: flex-start
        gap: 16px
        margin-top: 15px
        +rwdmax(767)
          gap: 12px
        .item
          width: calc(25% - 12px)
          border-radius: 12px
          overflow: hidden
          border: 1px solid rgba(255, 255, 255, 0.3)
          background-image: linear-gradient(180deg, rgba(255, 255, 255, 0.15) 0%, rgba(255, 255, 255, 0) 100%)
          opacity: 0
          transform: translateY(30px)
          +rwdmax(767)
            width: calc(25% - 9px)
          &:nth-child(1)
            transition: $transition .35s
          &:nth-child(2)
            transition: $transition .4s
          &:nth-child(3)
            transition: $transition .45s
          &:nth-child(4)
            transition: $transition .5s
          .inner
            width: 100%
            padding-bottom: 100%
            background-size: contain
            background-position: center
            background-repeat: no-repeat
</style>