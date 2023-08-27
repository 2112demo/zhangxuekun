<template lang="">
  <div class='box'>
    <div class='box-top'>
      <div>
        <span class="iconfont icon-cloud"></span>
        <h1 class='box-top-title'>{{msg}}</h1>
      </div>
    </div>
    <div class='nav'>

    </div>
  </div>
</template>
<script>
export default {
  name: 'navigator',
  props: {
    msg: String
  },
  data () {
    return {
      list: [
        {id: 1, name: '常用操作'}
      ]
    }
  }
}
</script>
<style lang="">
  .box-top{
    background-color: red;
    color: #fff;
  }
  .box-top div{
    display: flex;
    height: 64px;
    justify-content: center;
    align-items: center;
  }
  .icon-cloud{
    font-size: 30px;
  }
  .box-top-title{
    margin-left: 6px;
    font-size: 18px;
  }
</style>
