<template>
    <div>
      <home-header></home-header>
      <home-swiper :list="swiperList"></home-swiper>
      <home-icons :list="iconList"></home-icons>
      <home-recommend :list="recommendList"></home-recommend>
      <home-weekend :list="weekendList"></home-weekend>
    </div>
</template>

<script>
import HomeHeader from './components/Header.vue'
import HomeSwiper from './components/Swiper.vue'
import HomeIcons from './components/Icon.vue'
import HomeRecommend from './components/Recommend.vue'
import HomeWeekend from './components/Weekend.vue'
import axios from 'axios'
import { mapState } from 'vuex'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: [],
      lastCity:null,
    }
  },
  computed:{
    ...mapState(['city'])
  },
  methods: {
    getHomeInfo: function () {
      axios.get('./api/index.json?city='+this.city).then(
        this.getHomeInfoSucc
      )
    },
    getHomeInfoSucc: function (res) {
      console.log(res)
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        // this.city = data.city
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted: function () { // 组件被重新挂在的时候执行
    this.lastCity = this.city;
    console.log('mounted');
    this.getHomeInfo()
  },
  activated:function(){ // 页面显示的时候执行 keep-alive 新增的生命周期函数 
    console.log('activated');
    if(this.lastCity != this.city){
      this.lastCity = this.city
      this.getHomeInfo();
    }
  }
}
</script>

<style>
</style>
