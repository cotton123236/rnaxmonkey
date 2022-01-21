<script setup>
import { reactive } from 'vue'

const featureBlockData = reactive([
  {
    img: 'feature-01.png',
    title: 'Play to Earn',
    brief: 'The RNAxMonkey 3D Play-to-Earn games are designed togive you several exciting gameplay options, each one earning you in-game tokens!'
  },
  {
    img: 'feature-02.png',
    title: 'Minting',
    brief: 'The RNAxMonkey NFTs can be minted in our website using our native token, giving our token a true utilityand adding to its value.'
  },
  {
    img: 'feature-03.png',
    title: 'NFT STAKING',
    brief: 'The basic computing power of our Genesis NFT isshown as being between 100-300 power units. The better the quality of Genesis NFT, the higher the poweramount. The higher the player\'s NFT mining power, the more profit is realized.'
  },
  {
    img: 'feature-04.png',
    title: '3D Gaming',
    brief: 'Virtual reality will be implemented in the game, but havingvirtual reality glasses or other virtual reality relatedparaphernalia will not be a requirement for playing thegame.'
  },
  {
    img: 'feature-05.png',
    title: 'Expedition',
    brief: 'Build a team to eliminate enemies in the game. Every monkey has genetic characteristics, make a good arrangement of your monkeys team and winrewards with your team.'
  },
  {
    img: 'feature-06.png',
    title: 'Season',
    brief: 'Battle in the season mode and try to get a high ranking to get more token rewards.'
  },
])
</script>

<template>
  <section class="feature-block space-lr">
    <div class="block-content maxw-1200">
      <div class="term">FEATURES</div>
      <div class="content-items">
        <div class="each-feature"
        v-for="item in featureBlockData"
        :key="item.img"
        >
          <div class="photo-box">
            <div class="photo">
              <div class="image">
                <img :src="`/src/assets/image/home/${item.img}`"/>
              </div>
            </div>
          </div>
          <div class="text-box">
            <div class="title">{{ item.title }}</div>
            <p class="brief">{{ item.brief }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="sass" scoped>
@import './../../assets/sass/mixins'

.feature-block
  position: relative
  padding-top: 60px
  padding-bottom: 60px
  .content-items
    display: flex
    flex-wrap: wrap
    gap: 30px
    margin-top: 60px
    +rwdmax(767)
      gap: 20px
      margin-top: 30px
  .each-feature
    width: calc( 33.33% - 20px )
    border-radius: 12px
    border: 1px solid rgba(255, 255, 255, .3)
    min-height: 415px
    padding: 20px
    transition: .5s
    +rwdmax(1024)
      width: calc( 50% - 15px )
    +rwdmax(767)
      width: calc( 50% - 10px )
    +rwdmax(550)
      width: 100%
      min-height: auto
    &:hover
      transform: translateY(-5px)
      border-color: $pink-light
      .title
        color: $pink-light
    .photo
      position: relative
      width: 100%
      padding-bottom: 50%
      border-radius: 8px
      overflow: hidden
    .text-box
      padding-top: 30px
    .title
      font-size: px(28)
      line-height: 1.2
      font-weight: 600
      transition: $transition
      +rwdmax(1024)
        font-size: px(22)
    .brief
      font-size: px(14)
      line-height: 1.5
      margin-top: 15px
</style>