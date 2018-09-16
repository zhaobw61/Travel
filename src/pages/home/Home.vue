<template>
    <div>
      <home-hearder></home-hearder>
      <home-swiper></home-swiper>
      <home-icon></home-icon>
    </div>
</template>

<script>
import HomeHearder from './components/Header.vue'
import HomeSwiper from './components/Swiper.vue'
import HomeIcon from './components/Icon.vue'
export default {
  name: 'Home',
  components: {
    HomeHearder: HomeHearder,
    HomeSwiper: HomeSwiper,
    HomeIcon: HomeIcon
  }
}
</script>

<style>
</style>
