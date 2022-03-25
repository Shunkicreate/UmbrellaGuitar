<script>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
// import HelloWorld from './components/HelloWorld.vue'
// import Hiroki from './components/Hiroki.vue'
// import GUCCI from './components/GUCCI.vue'
// import Yukina from './components/Yukina.vue'

import Code from './components/Code.vue'
import Body from './components/Body.vue'

export default {
  components: {
    Code,
    Body
  }
}
</script>

<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <Hiroki></Hiroki>
  <Gucci></Gucci>
  
  <HelloWorld msg="Hello Vue 3 + TypeScript + Vite" /> -->
  <div>
  <Code></Code>  
  <Body></Body>
  </div>
</template>

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
