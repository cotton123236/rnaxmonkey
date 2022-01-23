<script setup>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
// import Home from './pages/Home.vue'
import './assets/sass/reset.sass'
import './assets/sass/common.sass'
</script>

<template>
  <Header />
  <main>
    <!-- Home -->
    <router-view></router-view>
  </main>
  <Footer />
</template>

<style lang="sass">
main
  padding-top: 100px
</style>
