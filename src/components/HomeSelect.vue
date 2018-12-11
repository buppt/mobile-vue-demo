<template>
  <div class="main">
    <div id="slider" class="slider">
      <img v-for="(src,index) in imgSrc" :key="index" :src="src"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeSlider',
  data () {
    return {
      imgSrc:[
        '../static/img/selectImg_03.jpg',
        '../static/img/selectImg_04.jpg',
        '../static/img/selectImg_05.jpg',
        '../static/img/selectImg_06.jpg',
        '../static/img/selectImg_07.jpg',
        '../static/img/selectImg_09.jpg',
        '../static/img/selectImg_10.jpg',
        '../static/img/selectImg_11.jpg',
        '../static/img/selectImg_12.jpg',
        '../static/img/selectImg_13.jpg'
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
      slider.style.marginLeft=`-${330*index}px`;
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
  width: 320px;
  margin: 0 auto;
  .slider{
    img{
      width: 64px;
      display: inline;
      margin: 0;
    }
  }
  
}
</style>
