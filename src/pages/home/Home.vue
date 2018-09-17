<template>
    <div>
      <home-hearder></home-hearder>
      <home-swiper></home-swiper>
      <home-icon></home-icon>
      <home-recommend></home-recommend>
      <home-weekend></home-weekend>
    </div>
</template>

<script>
import HomeHearder from './components/Header.vue'
import HomeSwiper from './components/Swiper.vue'
import HomeIcon from './components/Icon.vue'
import HomeRecommend from './components/Recommend.vue'
import HomeWeekend from './components/Weekend.vue'
export default {
  name: 'Home',
  components: {
    HomeHearder: HomeHearder,
    HomeSwiper: HomeSwiper,
    HomeIcon: HomeIcon,
    HomeRecommend: HomeRecommend,
    HomeWeekend:HomeWeekend
  }
}
</script>

<style>
</style>
