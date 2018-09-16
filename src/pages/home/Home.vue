<template>
    <div>
      <home-hearder></home-hearder>
      <home-swiper></home-swiper>
    </div>
</template>

<script>
import HomeHearder from './components/Header.vue'
import HomeSwiper from './components/Swiper.vue'
export default {
  name: 'Home',
  components: {
    HomeHearder: HomeHearder,
    HomeSwiper: HomeSwiper
  }
}
</script>

<style>
</style>
