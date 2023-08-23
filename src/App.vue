<template>
  <div id="app">
    <div class="leftbar">
      自定义组件 components
    </div>
    <div class="rightContent">
      <router-view/>
    </div>

  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  background-color: aqua;
  width: 100vw;
  height: 100vh;
}
.leftbar{
  background-color: red;
}
</style>
