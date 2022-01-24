<script setup>
import { computed, reactive } from 'vue'

const tokenBlockData = reactive({
  title: 'RNAxMONKEY TOKEN',
  brief: 'RNAXMONKEY Token($RMK) is the governance currency of RNAXMONKEY Metaverse. It will be used for trading, exchanging and breeding monkeys in the game.',
  num: 100000000
})

const currencyNum = computed(() => {
  const parts = tokenBlockData.num.toString().split('.');
  parts[0] = parts[0].replace(/\B(?=(\d{3})+(?!\d))/g, ',');
  return parts.join('.');
})
</script>

<template>
  <section class="token-block space-lr">
    <div class="block-content maxw-1200">
      <div class="content-left" data-aos="fade">
        <div class="title">{{ tokenBlockData.title }}</div>
        <p class="brief">{{ tokenBlockData.brief }}</p>
        <div class="token-box">
          <div class="sub-title">Contract</div>
          <p>Coming Soon</p>
        </div>
        <a class="pill-btn fill" href="javascript:;" target="_blank"><span>Buy $RMK</span></a>
      </div>
      <div class="content-right" data-aos="fade">
        <div class="sub-title">Total Supply</div>
        <div class="num">{{ currencyNum }}</div>
        <img src="/src/assets/image/home/token.png" alt="">
      </div>
    </div>
  </section>
</template>

<style lang="sass" scoped>
@import './../../assets/sass/mixins'

.token-block
  position: relative
  padding-top: 60px
  padding-bottom: 60px
  .block-content
    display: flex
    align-items: center
    +rwdmax(900)
      flex-direction: column
  .content-left
    width: 50%
    display: flex
    flex-direction: column
    align-items: flex-start
    padding-right: 30px
    +rwdmax(900)
      width: 100%
      padding-right: 0
    .title
      font-size: px(36)
      font-weight: 600
      line-height: 1.2
      color: $pink-light
      +rwdmax(1024)
        font-size: px(30)
    p
      font-size: px(14)
      line-height: 1.3
      font-weight: 500
      color: $gray
      &.brief
        margin-top: 15px
    .token-box
      width: 100%
      max-width: 480px
      padding: 20px 28px
      border-radius: 12px
      margin-top: 30px
      background-color: #131a20
      .sub-title
        font-size: px(20)
        line-height: 1.2
        font-weight: 500
        +rwdmax(767)
        font-size: px(18)
      p
        margin-top: 10px
    .pill-btn
      margin-top: 30px
  .content-right
    width: 50%
    +rwdmax(900)
      width: 100%
      max-width: 600px
      margin-top: 50px
    .sub-title
      text-align: center
      font-size: px(14)
      font-weight: 600
      line-height: 1.2
    .num
      text-align: center
      font-size: px(36)
      font-weight: 600
      line-height: 1.2
      color: $pink-light
      margin-bottom: 20px
      +rwdmax(1024)
        font-size: px(30)
      +rwdmax(767)
        font-size: px(26)
</style>