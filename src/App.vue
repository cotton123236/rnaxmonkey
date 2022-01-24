<script setup>
import { onMounted } from 'vue'
import AOS from 'aos'
import 'aos/dist/aos.css'

import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
// import Home from './pages/Home.vue'
import './assets/sass/reset.sass'
import './assets/sass/common.sass'

onMounted(() => {
  AOS.init({
    duration: 800,
    offset: 200,
    once: true
  })
})

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
