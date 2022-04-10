<script lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
// import HelloWorld from './components/HelloWorld.vue'
import Hiroki from './components/Hiroki.vue'
import GUCCI from './components/GUCCI.vue'
import Yukina from './components/Yukina.vue'
import { defineComponent } from 'vue';
import V from './components/V.vue'

export default defineComponent({
  components: {
    Hiroki,
    GUCCI,
    Yukina,
    V
  }
})
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />aaaaaaa
  <Hiroki></Hiroki>
  <GUCCI></GUCCI>
  <V></V>
  <Yukina></Yukina>
  <HelloWorld msg="Hello Vue 3 + TypeScript + Vite" />
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

#app .logo {
  text-align: center;
  background: #fff;
}
#app .logo img{
  height: 100px;
}
#app .main-container {
  padding-top: 40px;
}

.container{
  margin: 0 auto;
  width: 100%;
  max-width: 980px;
  background: #eee;
}
</style>
