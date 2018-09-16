<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide v-for="item of swiperList" :key="item.id">
          <img class="swiper-img" :src="item.imgUrl">
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://img1.qunarzz.com/qs/1808/4d/077b11817a69b102.jpg'
      }, {
        id: '0002',
        imgUrl: 'https://img1.qunarzz.com/qs/1809/cb/25012195ae916f02.jpg'
      }]
    }
  }
}
</script>

<style lang='stylus' scoped>
  .wrapper >>> .swiper-pagination-bullet-active{
    background : #fff;
  }
  .wrapper{
    overflow :hidden;
    width :100%;
    height : 0;
    // padding-bottom: 31.25%;
    padding-bottom: 25.25%;
    background :#ccc;
    .swiper-img{
      width:100%;
    }
  }
</style>
