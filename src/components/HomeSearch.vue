<template>
  <div class="main">
      <div class="time">
        <span class="place"><b>北京</b></span> <span class="split">|</span> <b>11.02</b>入住 - <b>11.03</b>退房
      </div>
      <hr/>
      <div class="search">
          <input type="text" placeholder="位置/地标/房源标题(选填)"/>
          <button>查找</button>
      </div>
  </div>
</template>

<script>
export default {
  name: 'HomeSearch',
  data () {
    return {

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='less' scoped>
@gray: rgb(220, 220, 220);
@yellow: rgb(250, 223, 118);
.main{
    height: 100px;
    width: 360px;
    margin: 0 auto;
    box-shadow: 0 0 10px @gray;
    text-align: left;
    .time{
        height: 49px;
        line-height: 50px;
        margin-left: 20px; 
        .place{
          margin-right: 30px;
        }
        .split{
          color: @gray;
          margin-right: 10px;
        }
    }
    hr{
      height: 1px;
      margin: 0 10px;
      border: 0;
      border-top: 1px solid @gray
    }
    .search{
      height: 49px;
      line-height: 50px;
      margin-left: 20px; 
      input{
        width: 215px;
        height: 40px;
        font-size: 16px;
        border: 0;
        outline: none;
      }
      button{
        background-color: @yellow;
        border: 0;
        height: 35px;
        width: 107px;
        font-weight: 900;
        font-size: 17px;
        border-radius: 3px;
      }
    }
}
</style>
