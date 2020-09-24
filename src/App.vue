<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <HelloWorld :width='width' :height='height' msg="Welcome to Your Vue.js App" class="body"/>
    <TransimitionTest></TransimitionTest>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TransimitionTest from './components/TransimitionTest'

export default {
  name: 'App',
  data:function() {
  return {
    width:document.documentElement.clientWidth,
    height:document.documentElement.clientHeight
  };
},
  components: {
    HelloWorld,
    TransimitionTest
  },
  mounted(){
    window.onresize = () => {
      this.width=document.documentElement.clientWidth;
      this.height=document.documentElement.clientHeight;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 800px;
}

.body {
  height: 100%;
}
</style>
