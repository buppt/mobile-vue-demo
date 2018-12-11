<template>
  <div class="main">
    <div class="title">民宿清单</div>
    <div id="list" class="slider">
      <img v-for="(src,index) in imgSrc" :key="index" :src="src" 
      @touchstart="touchstart"
      @touchmove="touchmove"
      @touchend="touchend"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Homelist',
  data () {
    return {
      imgSrc:[
        '../static/img/list_01.jpeg',
        '../static/img/list_02.jpeg',
        '../static/img/list_03.jpeg',
        '../static/img/list_04.jpeg',
      ],
      startPointX: 0,
      changePointX: 0,
      showIndex: 0,
      slider: null,
      originMargin: 0,
    }
  },
  methods:{
    touchstart(e){
      this.startPointX = e.changedTouches[0].pageX;
      let slider = document.getElementById('list');
      this.slider = slider;
      this.originMargin = slider.style.marginLeft;
    },
    touchmove(e){
      if(this.startPointX==this.changePointX){
        return ;
      }
      let currPointX = e.changedTouches[0].pageX;
      let leftSlide = this.startPointX-currPointX;
      if(!this.originMargin){
        this.slider.style.marginLeft = `-${leftSlide}px`;
      }else{
        let currentMargin = parseInt(this.originMargin) - leftSlide;
        this.slider.style.marginLeft = `${currentMargin}px`;
      }
    },
    touchend(e){
      let originMargin = parseInt(this.slider.style.marginLeft);
      console.log(originMargin);
      
      if(originMargin>0){
        this.slider.style.marginLeft=0;
        return;
      }
      if(originMargin<-510){
        this.slider.style.marginLeft=`-${510}px`;
        return;
      }
    }
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
.main{
  width: 100%;
  .title{
    width: 320px;
    margin: 0 auto;
    margin-top: 20px;
    margin-bottom: 10px; 
    text-align: left;
    font-size: 18px;
    font-weight: 900;
  }
  .slider{
    overflow: hidden;
    white-space: nowrap;
    // transition: 1s; 
    padding: 0 calc(50vw - 160px);
    img{
      width: 200px;
      display: inline;
      margin-right: 10px;
    }
  }
  
}
</style>
