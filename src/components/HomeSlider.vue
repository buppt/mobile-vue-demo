<template>
  <div class="main">
    <div class="title">今日推荐<span class="number">{{showIndex+1}}<span class="littleNum">/{{this.imgSrc.length}}</span></span></div>
    <div id="slider" class="slider">
      <img v-for="(src,index) in imgSrc" :key="index" :src="src" 
      @touchstart="touchstart"
      @touchmove="touchmove"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeSlider',
  data () {
    return {
      imgSrc:[
        '../static/slider1.jpeg',
        '../static/slider2.jpeg',
        '../static/slider3.jpeg',
        '../static/slider4.jpeg',
        '../static/slider5.jpeg',
      ],
      startPointX: 0,
      changePointX: 0,
      showIndex: 0,
    }
  },
  methods:{
    show(index){
      this.changePointX=this.startPointX;
      let slider = document.getElementById('slider');
      slider.style.marginLeft=`-${370*index}px`;
    },
    touchstart(e){
      this.startPointX = e.changedTouches[0].pageX;
    },
    touchmove(e){
      if(this.startPointX==this.changePointX){
        return ;
      }
      let currPointX = e.changedTouches[0].pageX;
      let leftSlide = this.startPointX-currPointX;
      if(leftSlide>30&&this.showIndex<this.imgSrc.length-1){
        this.show(++this.showIndex)
      }else if(leftSlide<-30&&this.showIndex>0){
        this.show(--this.showIndex)
      }
    },
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
.main{
  width: 100%;
  
  .title{
    width: 360px;
    margin: 0 auto;
    margin-top: 20px;
    margin-bottom: 10px; 
    text-align: left;
    font-size: 18px;
    font-weight: 900;
    .number{
      float: right;
      .littleNum{
        font-size: 12px;
        font-weight: 300;
      }
    }
  }
  .slider{
    overflow: hidden;
    white-space: nowrap;
    transition: 1s; 
    padding: 0 calc(50vw - 180px);
    img{
      width: 360px;
      display: inline;
      margin-right: 10px;
    }
  }
  
}
</style>
