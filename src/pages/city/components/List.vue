<template>
    <div class="list" ref='wrapper'>
        <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button">{{this.currentCity}}</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom" @click="handleCityClick('item.name')">热门城市</div>
                <div class="button-list">
                    <div 
                        class="button-wrapper" 
                        v-for="item of hot"
                        :key = "item.id"
                        @click="handleCityClick(item.name)"
                    >
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div class="area" 
                v-for="(item,key) of cities" 
                :key="key"
                :ref="key"
            >
                <div class="title border-topbottom">{{key}}</div>
                <div class="item-list">
                    <div 
                    class="item border-bottom"
                    v-for="innerItem of item" 
                    :key="innerItem.id"
                    @click="handleCityClick(innerItem.name)"
                >
                    {{innerItem.name}}</div>
                </div>
            </div>
        </div>
    </div>    
</template>
<script>
import Bscroll from 'better-scroll'
import {mapState,mapMutations} from 'vuex'
export default {
  name: "CityList",
  props:{
      hot:Array,
      cities:Object,
      letter:String
  },
  computed:{
      ...mapState({
          currentCity:'city'
      })
  },
  mounted:function(){
      this.scroll = new Bscroll(this.$refs.wrapper,{
          click:true
      })
  },
  watch:{
      letter:function(){
          console.log(this.$refs[this.letter])
          if(this.letter){
            this.scroll.scrollToElement(this.$refs[this.letter][0]);
          }
      }
  },
  methods:{
      handleCityClick:function(city){
        // this.$store.dispatch('changeCity',city);
        this.changeCity(city)
        this.$router.push('/');
      },
      ...mapMutations(['changeCity'])
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varbles.styl';

.border-topbottom: {
    &:before {
        border-color: #ccc;
    }

    &:a fter {
        border-color: #ccc;
    }
}

.border-bottom {
    &:before {
        border-color: #ccc;
    }
}

.list {
    position: absolute
    top : 1.58rem
    left: 0
    right : 0
    bottom : 0
    overflow hidden
    .title {
        line-height: 0.54rem;
        background: #eeeeee;
        padding-left  0.2rem
        color: #666;
        font-size: 0.26rem;        
    }

    .button-list {
        overflow: hidden;
        padding: 0.1rem 0.6rem 0.1rem 0.1rem;

        .button-wrapper {
            float: left;
            width: 33.33%;

            .button {
                margin: 0.1rem;
                padding: 0.1rem 0;
                text-align: center;
                border: 0.02rem solid #ccc;
                border-radius: 0.06rem;
            }
        }
    }

    .item-list {
        .item {
            line-height: 0.76rem;
            padding-left: 0.2rem;
        }
    }
}
</style>
