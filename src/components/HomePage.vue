<template>
  <div class="hello">
    <h3>榛果民宿</h3>
    <home-search></home-search>
    <home-slider></home-slider>
    <img src="../../static/welfare.jpeg"/>
    <home-select></home-select>
    <home-ad></home-ad>
    <home-list></home-list>
  </div>
</template>

<script>
import HomeSearch from './HomeSearch'
import HomeSlider from './HomeSlider'
import HomeSelect from './HomeSelect'
import HomeAd from './HomeAd'
import HomeList from './HomeList'
export default {
  name: 'HomePage',
  components:{
    HomeSearch,HomeSlider,HomeSelect,HomeAd,HomeList
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
img{
  width: 320px;
  margin: 10px auto;
}
</style>
