<template>
  <div id="app">
    <div class="leftBar">
      <!-- 自定义组件 components -->
      <navigation msg="骑得快外卖在线送餐" />
    </div>
    <div class="rightContent">
      <router-view/>
    </div>

  </div>
</template>

<script>
import navigation from './components/navigation.vue'

export default {
  name: 'App',
  components: {
    navigation
  }
}
</script>
<style>
@import "./assets/font/iconfont.css";
*{margin: 0;padding: 0;list-style: none;}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  width: 100vw;
  height: 100vh;
}
.leftBar{
  background-color: #fff;
  width: 15vw;
}
.rightContent{
  background-color: #f5f5f5;
  flex: 1;
}
</style>
