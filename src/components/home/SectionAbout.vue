<script setup>
import { reactive } from 'vue'

const aboutBlockData = reactive({
  title: 'ABOUT RNA x MONKEY',
  brief: 'The RNAxMonkey 3D Play-to-Earn games are designed togive you several exciting gameplay options, each one earningyou in-game tokens!<br><br>The 3D game will be playable online and is therefore notlimited by your choice of smart device nor by your choice ofoperating system, as long as the smart device has enoughcomputing power to run the game.'
})
</script>

<template>
  <section class="about-block space-lr">
    <div class="block-content maxw-1200">
      <div class="content-photo">
        <img src="/src/assets/image/home/about-01.png">
      </div>
      <div class="content-text">
        <div class="title">{{ aboutBlockData.title }}</div>
        <p class="brief" v-html="aboutBlockData.brief"></p>
      </div>
    </div>
  </section>
</template>

<style lang="sass" scoped>
@import './../../assets/sass/mixins'

.about-block
  position: relative
  padding-top: 75px
  padding-bottom: 75px
  overflow: hidden
  +rwdmax(767)
    padding-top: 40px
    padding-bottom: 60px
  .block-content
    position: relative
    display: flex
    align-items: center
    +rwdmax(900)
      display: block
  .content-photo
    width: 30%
    max-width: 310px
    +rwdmax(900)
      width: 200px
    +rwdmax(767)
      width: 150px
  .content-text
    flex: 1
    margin-left: 80px
    +rwdmax(900)
      margin-left: 0
      margin-top: -260px
    +rwdmax(767)
      margin-top: -200px
    .title
      font-size: px(58)
      font-weight: 700
      line-height: 1.2
      color: $pink-light
      +rwdmax(1024)
        font-size: px(42)
      +rwdmax(900)
        display: flex
        align-items: center
        padding-left: 200px
        height: 265px
      +rwdmax(767)
        height: 200px
        font-size: px(30)
        padding-left: 150px
    .brief
      font-size: px(16)
      font-weight: 500
      line-height: 1.3
      margin-top: 35px
      +rwdmax(900)
        margin-top: 20px
</style>