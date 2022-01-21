<script setup>
</script>

<template>
  <header class="space-lr">
    <div class="container">
      <router-link class="logo" to="/">
        <img src="./../assets/image/logo.svg" alt="logo"/>
      </router-link>
      <nav>
        <router-link class="links" to="/">Home</router-link>
        <router-link class="links disable" to="/">Coming Soon</router-link>
        <router-link class="links disable" to="/">Coming Soon</router-link>
        <router-link class="links disable" to="/">Coming Soon</router-link>
        <router-link class="links disable" to="/">Coming Soon</router-link>
      </nav>

    </div>
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
  height: 100px
  background-color: $black
  .container
    display: flex
    align-items: center
    height: 100%
  .logo
    width: 130px
    margin-right: 60px
  nav
    +rwdmax(1024)
      display: none
  .links
    font-size: px(16)
    font-weight: 600
    line-height: 1.5
    margin: 0 20px
    transition: $transition
    &.disable
      pointer-events: none
      opacity: .7
</style>