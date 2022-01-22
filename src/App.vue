<script setup>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Home from './pages/Home.vue'
</script>

<template>
  <Header />
  <main>
    <Home />
  </main>
  <Footer />
</template>

<style lang="sass">
@import './assets/sass/reset'
@import './assets/sass/common'

main
  padding-top: 100px
</style>
