<template lang="">
  <div id='box'>
    <!-- <div class='box-left'>123</div> -->
    <div class='box-right'>123</div>
  </div>
</template>
<script>
export default {
  name: 'index'
}
</script>
<style lang="">
  *{margin: 0;padding: 0;list-style: none;}
  #app{
    margin: 0;padding: 0;
  }
  #box{
    display: flex;
  }
  .box-left{
    width: 15vw;
    height: 100vh;
    background-color: #ffffff;
  }
  .box-right{
    width: 85vw;
    height: 100vh;
    background-color: #f5f5f5;
  }
</style>
