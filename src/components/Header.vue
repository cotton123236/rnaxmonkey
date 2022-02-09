<script setup>
import { ref, reactive } from 'vue'
import Menu from './Menu.vue'

import tele from './../assets/icon/telegram.svg'
import twit from './../assets/icon/twitter.svg'
import enve from './../assets/icon/envelope.svg'

const unit = reactive([
  {
    href: 'javascript:;',
    name: 'Home',
    isDisable: false
  },
  {
    href: 'javascript:;',
    name: 'Playnow',
    isDisable: true
  },
  {
    href: 'javascript:;',
    name: 'Marketplace',
    isDisable: true
  },
  {
    href: 'javascript:;',
    name: 'Farm',
    isDisable: true
  },
  {
    href: 'javascript:;',
    name: 'Whitepaper',
    isDisable: false
  },
  {
    href: 'javascript:;',
    name: 'Learn More',
    isDisable: false
  }
])

const isMenuActive = ref(false)

const socialIocn = reactive([
  {
    href: 'https://t.me/RnaxMonkey_Official',
    img: tele
  },
  {
    href: 'https://twitter.com/rnamonkey?s=11',
    img: twit
  },
  {
    href: 'mailto:Maxmonkey@gmail.com',
    img: enve
  },
])

const menuControl = () => {
  isMenuActive.value = !isMenuActive.value
}
</script>

<template>
  <header class="space-lr">
    <div class="container">
      <router-link class="logo" to="/">
        <img src="./../assets/image/logo.png" alt="logo"/>
      </router-link>
      <nav>
        <a
        class="links"
        :href="item.href"
        :class="{disable: item.isDisable}"
        v-for="item in unit"
        :key="item.name"
        >
        {{ item.name }}
        </a>
      </nav>
      <div class="social-box">
        <a
        v-for="item in socialIocn"
        :key="item"
        :href="item.href"
        target="_blank"
        >
          <img :src="item.img" alt="">
        </a>
      </div>
      <a
      href="javascript:;"
      class="menu-btn"
      @click="menuControl"
      >
        <span></span><span></span><span></span>
      </a>
    </div>
    <Menu
    :unitItems="unit"
    :isActive="isMenuActive"
    @changeMenuStatus="menuControl"
    />
  </header>
</template>

<style lang="sass">
@import './../assets/sass/mixins'

header
  position: fixed
  z-index: 9
  top: 0
  left: 0
  width: 100%
  height: 80px
  background-color: $black
  overflow: hidden
  .container
    display: flex
    align-items: center
    height: 100%
  .logo
    width: 130px
    margin-right: 60px
  nav
    +rwdmax(1200)
      display: none
  .links
    display: inline-flex
    align-items: center
    font-size: px(16)
    font-weight: 600
    line-height: 1.5
    margin: 5px 15px
    transition: $transition
    &:hover
      &:not(.disable)
        transform: translateY(-3px)
    &.disable
      pointer-events: none
      opacity: .7
      &::after
        content: 'Coming Soon'
        display: inline-block
        font-size: px(12)
        font-weight: 600
        line-height: 1.5
        padding: 5px
        border-radius: 8px 0
        background-color: #1F2933
        margin-left: 8px
  .social-box
    display: flex
    align-items: center
    margin-left: auto
    a
      display: inline-block
      width: 30px
      transition: $transition
      &:hover
        transform: translateY(-3px)
      &:not(:last-child)
        margin-right: 12px
  .menu-btn
    display: none
    padding: 5px
    margin-left: 20px
    transition: $transition
    +rwdmax(1200)
      display: block
    &:hover
      transform: translateY(-3px)
    span
      display: block
      width: 25px
      height: 2px
      background-color: $pink
      margin: 5px 0

</style>