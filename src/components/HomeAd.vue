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
        '../static/img/ad_01.jpg',
        '../static/img/ad_02.jpg',
        '../static/img/ad_03.jpg',
        '../static/img/ad_04.jpg',
      ],
    }
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
.main{
  width: 320px;
  margin: 10px auto;
  .slider{
    img{
      width: 75px;
      display: inline;
      margin: 0;
      margin-right: 5px;
    }
    :last-child{
        margin: 0;
    }
  }
  
}
</style>
