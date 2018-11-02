<template>
  <div class="hello">
    <h3>榛果民宿</h3>
    <home-search></home-search>
    <home-slider></home-slider>
  </div>
</template>

<script>
import HomeSearch from './HomeSearch'
import HomeSlider from './HomeSlider'
export default {
  name: 'HomePage',
  components:{
    HomeSearch,HomeSlider,
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

</style>
