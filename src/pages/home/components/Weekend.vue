<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom"  v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper"> 
          <img class="item-img" :src = item.imgUrl alt="">
        </div>
        <div class="item-info">
          <p class="item-title">上海杜莎夫人蜡像馆</p>
          <p class="item-desc">上海杜莎夫人蜡像馆上海杜莎夫人蜡像馆上海杜莎夫人蜡像馆</p>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1704/c9/c936f3fccfc6d7eda3.img.jpg_200x200_46052773.jpg',
        title: '上海杜莎夫人蜡像馆',
        desc: '上海杜莎夫人蜡像馆上海杜莎夫人蜡像馆上海杜莎夫人蜡像馆'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1704/c9/c936f3fccfc6d7eda3.img.jpg_200x200_46052773.jpg',
        title: '上海杜莎夫人蜡像馆',
        desc: '上海杜莎夫人蜡像馆上海杜莎夫人蜡像馆上海杜莎夫人蜡像馆'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1704/c9/c936f3fccfc6d7eda3.img.jpg_200x200_46052773.jpg',
        title: '上海杜莎夫人蜡像馆',
        desc: '上海杜莎夫人蜡像馆上海杜莎夫人蜡像馆上海杜莎夫人蜡像馆'
      }]
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl'
  .title{
    margin-top :.2rem;
    line-height :.8rem;
    background : #ccc;
    text-indent: .2rem;
  }
  .item-img-wrappper{
    overflow hidden
    height 0
    padding=bottom 33.9%
  }
  .item-img{
    width: 100%;
  }
  .item-info{
    flex:1;
    paddind : .1rem;
    min-width : 0;
    .item-title{
      line-height :.54rem;
      font-size :.32rem;
      ellipsis();
    }
    .item-desc{
      line-height : .4rem;
      color : #ccc;
      ellipsis();
    }
    .item-button{
      line-height : .44rem;
      margin-top : .16rem;
      background :#ff9300;
      padding:0 .2rem;
      border-radius: .06rem;
      color :#fff;
    }
  }
</style>
