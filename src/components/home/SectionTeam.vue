<script setup>
import { reactive } from 'vue'

const teamBlockData = reactive([
  {
    id: '01',
    name: 'Robert',
    title: 'Chief Executive Officer',
    list: [
      'Years of entrepreneurial experience in the blockchain industry',
      'Experience in AR, VR and more',
      'User-oriented, artistic product design and development'
    ]
  },
  {
    id: '02',
    name: 'Andy W.',
    title: 'Chief Technology Officer',
    list: [
      'Extensive blockchain development experience',
      'Development experience in other related industries',
      'Mastered multiple game engines'
    ]
  },
  {
    id: '03',
    name: 'Danny C.',
    title: 'Chief Architect Officer',
    list: [
      'Full-stack engineer',
      'Multiple programming languages developed several educational',
      'Games using AT cards and blockchain services'
    ]
  },
  {
    id: '04',
    name: 'Robert',
    title: 'Chief Marketing Officer',
    list: [
      '3+ years of experience in project management',
      '3+ years of experience as management consultant'
    ]
  },
  {
    id: '05',
    name: 'Peter R.',
    title: 'Result-driven Management Consultant',
    list: [
      'Operational excellence',
      'Project management',
      'Business process improvement',
      'Business data analysis',
      'Agile methodologies'
    ]
  },
])
</script>

<template>
  <section class="team-block space-lr">
    <div class="block-content maxw-1200">
      <div class="term">MEET OUR TEAM</div>
      <div class="content-item">
        <div class="each-member"
        v-for="item in teamBlockData"
        :key="item.id">
          <div class="name">{{ item.name }}</div>
          <div class="title">{{ item.title }}</div>
          <ul>
            <li
            v-for="(list, index) in item.list"
            :key="index">{{ list }}</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="sass" scoped>
@import './../../assets/sass/mixins'

.team-block
  position: relative
  padding-top: 60px
  padding-bottom: 60px
  .content-item
    display: flex
    flex-wrap: wrap
    gap: 40px
    margin-top: 40px
    +rwdmax(767)
      gap: 20px
  .each-member
    display: flex
    flex-direction: column
    align-items: center
    width: calc(25% - 30px)
    border-radius: 12px
    border: 1px solid rgba(255, 255, 255, 0.3)
    padding: 30px 40px
    transition: $transition
    +rwdmax(1200)
      width: calc(50% - 20px)
    +rwdmax(600)
      width: 100%
    &:hover
      transform: translateY(-5px)
      border-color: $pink-light
      .name
        color: $pink-light
    &:first-child
      width: 100%
      .name
        font-size: px(36)
        +rwdmax(767)
          font-size: px(28)
      .title
        font-size: px(24)
        +rwdmax(767)
          font-size: px(20)
      ul
        margin-top: 25px
        width: auto
        +rwdmax(767)
          margin-top: 20px
    .name
      font-size: px(24)
      font-weight: 600
      line-height: 1.2
      text-align: center
      transition: $transition
      +rwdmax(767)
        font-size: px(20)
    .title
      font-size: px(18)
      font-weight: 600
      line-height: 1.5
      text-align: center
      margin-top: 5px
      +rwdmax(767)
        font-size: px(16)
    ul
      width: 100%
      font-size: px(14)
      line-height: 1.5
      color: #cbd2d9
      margin-top: 30px
      +rwdmax(767)
        margin-top: 20px
      li
        position: relative
        padding-left: 15px
        &::before
          top: 7px
          left: 0
          width: 4px
          height: 4px
          border-radius: 50%
          background-color: #fff
          +pseudo
</style>