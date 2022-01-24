<script setup>
</script>

<template>
  <footer data-aos="fade">
    <div class="incubat-wrap">
      <span>Incubated by</span>
      <img src="/src/assets/image/home/supporter-04.png">
    </div>
    <div class="copyright">Copyright © 2022 RNTxMonkey. All Rights Reserved.</div>
  </footer>
</template>

<style lang="sass" scoped>
@import './../assets/sass/mixins'

footer
  display: flex
  flex-direction: column
  align-items: center
  padding-top: 90px
  padding-bottom: 50px
  +rwdmax(1024)
    padding-top: 70px
  +rwdmax(767)
    padding-top: 50px
    padding-bottom: 40px
  .incubat-wrap
    +flex
    span
      font-size: px(14)
      margin-right: 12px
    img
      width: 150px
  .copyright
    font-size: px(12)
    line-height: 1.3
    text-align: center
    color: $gray
    margin-top: 70px
    +rwdmax(1024)
      margin-top: 60px
    +rwdmax(767)
      margin-top: 50px
</style>