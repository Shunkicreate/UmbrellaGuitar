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
  <div class="all">
    <div class="head">
      <div class="head_name">Umbrella Guitar</div>
      <div class="head_drag"><p>drag code and practice guitar</p></div>
    </div>
    <div class="nikai">
      <Yukina class="yuki"></Yukina>
      <div class="dansi">
        <Hiroki class="hirki"></Hiroki>
        <GUCCI class="gucci"></GUCCI>
      </div>
    </div>
    <V></V>
    <HelloWorld msg="Hello Vue 3 + TypeScript + Vite" />
  </div>
</template>

<style>
*{
  margin: 0%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2d3c4b;
  /* margin-top: 60px; */
}

#app .logo {
  text-align: center;
  background: #E9E9E8;
}
#app .logo img{
  height: 100px;
}
/* #app .main-container {
  padding-top: 40px;
} */
.head {
  padding-bottom: 0%;
  /* border-bottom: solid 2px black; */
  display: flex;
  justify-content: flex-start;
  height: 20%;
}
.head_name {
  font-family: cursive;
  font-size:  40px;
}

.head_drag {
  margin: auto;
}

.head_drag p{
  margin-bottom: 0px;
}

/* .container{
  margin: 0 auto;
  width: 100%;
  max-width: 980px;
  background: #eee;
} */

.all {
  background-color: #E9E9E8;
}

.yuki {
  height: 80%;
  width: 30%;
}

.hiroki {
  height: 20%;
  width: 70%;
}

.gucchi {
  height: 80%;
  width: 70%;
}

.nikai {

  display: flex;

}

</style>
