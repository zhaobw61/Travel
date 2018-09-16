<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-imgcontent" :src=item.imgUrl alt="">
          </div>
          <p class='icon-desc'>{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcon',
  data: function () {
    return {
      swiperOption: {
        loop: true
      },
      iconList: [{
        id: '001',
        imgUrl: 'https://s.qunarzz.com/package_mobile/app/home/icon-local.png',
        desc: '景点门票'
      }, {
        id: '002',
        imgUrl: 'https://s.qunarzz.com/package_mobile/app/home/icon-local.png',
        desc: '景点门票'
      }, {
        id: '003',
        imgUrl: 'https://s.qunarzz.com/package_mobile/app/home/icon-local.png',
        desc: '景点门票'
      }, {
        id: '004',
        imgUrl: 'https://s.qunarzz.com/package_mobile/app/home/icon-local.png',
        desc: '景点门票'
      }, {
        id: '005',
        imgUrl: 'https://s.qunarzz.com/package_mobile/app/home/icon-local.png',
        desc: '景点门票'
      }, {
        id: '006',
        imgUrl: 'https://s.qunarzz.com/package_mobile/app/home/icon-local.png',
        desc: '景点门票'
      }, {
        id: '007',
        imgUrl: 'https://s.qunarzz.com/package_mobile/app/home/icon-local.png',
        desc: '景点门票'
      }, {
        id: '008',
        imgUrl: 'https://s.qunarzz.com/package_mobile/app/home/icon-local.png',
        desc: '景点门票'
      }, {
        id: '008',
        imgUrl: 'https://s.qunarzz.com/package_mobile/app/home/icon-local.png',
        desc: '景点门票'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varbles.styl'
@import '~styles/mixins.styl'
  .icons >>> .swiper-container{
    height :0;
    padding-bottom : 50%;
  }
  .icon{
    position relative;
    overflow :hidden;
    float: left;
    width:25%;
    height 0;
    padding-bottom:25%;
    background : #ccc;
    .icon-umg{
      position absolute;
      top: 0;
      left 0;
      right 0;
      bottom .44rem;
      box-sizing : border-box;
      padding  .1rem;
      background blue;
      .icon-imgcontent{
        display :block;
        margin 0 auto;
        height 100%;
      }
    }
    .icon-desc{
      position :absolute;
      left :0;
      right :0;
      bottom 0;
      height: .44rem;
      line-height :.44rem;
      text-align :center;
      color: $darkTextColor;
      ellipsis();
    }
  }
</style>
