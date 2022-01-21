<script setup>
import { reactive } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'

const charaBlockData = reactive([
  {
    name: 'Goku',
    img: 'chara-01.png',
    icon: 'chara-ele-01.png',
    ele: 'Light',
    item: ['chara-01-item-01.png', 'chara-01-item-02.png', 'chara-01-item-03.png', 'chara-01-item-04.png']
  },
  {
    name: 'Quinn',
    img: 'chara-02.png',
    icon: 'chara-ele-02.png',
    ele: 'Fire',
    item: ['chara-02-item-01.png', 'chara-02-item-02.png', 'chara-02-item-03.png', 'chara-02-item-04.png']
  },
  {
    name: 'Singed',
    img: 'chara-03.png',
    icon: 'chara-ele-03.png',
    ele: 'Earth',
    item: ['chara-03-item-01.png', 'chara-03-item-02.png', 'chara-03-item-03.png', 'chara-03-item-04.png']
  }
])

</script>

<template>
  <section class="chara-block space-lr">
    <div class="block-content maxw-1200">
      <div class="term">GAME CHARACTER</div>
      <div class="content-item">
        <swiper
        navigation
        >
          <swiper-slide
          v-for="item in charaBlockData"
          :key="item.img"
          >
            <div class="slide-inner">
              <div class="photo-box">
                <div class="photo">
                  <div class="image">
                    <img :src="`/src/assets/image/home/${item.img}`" alt="">
                  </div>
                </div>
              </div>
              <div class="text-box">
                <div class="sub-term">
                  <div class="icon"><img :src="`/src/assets/image/home/${item.icon}`" alt=""></div>
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
                      <div class="inner" :style="{ backgroundImage: `url(/src/assets/image/home/${part})` }"></div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </swiper-slide>
        </swiper>
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
  .slide-inner
    display: flex
    align-items: center
    padding-top: 30px
    .photo-box
      width: 35%
      max-width: 310px
    .photo
      position: relative
      width: 100%
      padding-bottom: 133.33%
    .text-box
      flex: 1
      padding-left: 65px
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
      .ele
        font-size: px(14)
        font-weight: 500
        line-height: 1.5
        color: $gray
        span
          color: #fff
    .parts
      margin-top: 40px
      .title
        font-size: px(14)
        font-weight: 500
        line-height: 1.5
      .items
        display: flex
        align-items: flex-start
        gap: 16px
        margin-top: 15px
        .item
          width: calc(25% - 12px)
          border-radius: 12px
          overflow: hidden
          border: 1px solid rgba(255, 255, 255, 0.3)
          background-image: linear-gradient(180deg, rgba(255, 255, 255, 0.15) 0%, rgba(255, 255, 255, 0) 100%)
          .inner
            width: 100%
            padding-bottom: 100%
            background-size: contain
            background-position: center
            background-repeat: no-repeat
</style>