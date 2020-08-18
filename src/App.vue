<template>
  <div id="app">
    <img alt="vs logo" src="./assets/vs.png" />
    <HelloWorld msg />
    <h1>{{total}}</h1>
    <div class="row">
      <!---รีบค่า emit @cc แล้วส่งไปทำงานที่ function "sum"--->
      <div class="col-12"><warzone start="start"/></div>
        <Counter label="Wow" @cc="sum" />
      </div>
      </div>
  
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import warzone from "./components/warzone.vue"

export default {
  name: "App",
  components: {
    HelloWorld,
    warzone,
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
