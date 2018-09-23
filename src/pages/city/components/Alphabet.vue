<template>
    <ul class="list">
        <li 
            class="item" 
            v-for="item of letters" 
            :key="item"
            :ref="item"
            @touchstart="handleTouchStart"
            @touchmove="handleTouchMove"
            @touchend="handleTouchEnd"
            @click="handleLetterClick"
        >{{item}}</li>
    </ul>  
</template>
<script>

export default {
  name: "CityAlphaber",
  props:['cities'],
  computed:{
      letters:function(){
          var letters = []
          for(var i in this.cities){
              letters.push(i);
          }
          return letters;
      }
  },
  data:function(){
      return {
          touchStatus:false,
          startY:0,
          timer:null
      }
  },
  updated:function(){
      this.startY = this.$refs['A'][0].offsetTop;
  },
  methods:{
      handleLetterClick:function(e){
          console.log(e.target.innerText);
          var text = e.target.innerText;
          this.$emit('change',text)
      },
      handleTouchStart:function(){
          console.log('handleTouchStart');
          this.touchStatus = true;
      },
      handleTouchMove:function(e){
          if(this.touchStatus){
              if(this.timer){
                  clearTimeout(this.timer)
              }
              this.timer = setTimeout(function(){
                var touchY = e.touches[0].clientY - 79;
                var index = Math.floor((touchY - this.startY)/20);
                if(index>=0&&index<=this.letters.length){
                    this.$emit('change',this.letters[index]);
                }
                console.log(index);
              }.bind(this),16)
          }
      },
      handleTouchEnd:function(){
          this.touchStatus = false;
      }
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varbles.styl';
.list{
    display :flex
    flex-direction : column
    justify-content:center
    position: absolute
    top: 1.58rem;
    right: 0
    bottom: 0
    width : .4rem
    .item{
        line-height : .4rem
        text-align: center
        color  $bgColor
    }
}
</style>
