<script lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
// import HelloWorld from './components/HelloWorld.vue'
import { provide, reactive, ref } from 'vue'
import MyMap from './components/MyMap.vue'
import Hiroki from './components/Hiroki.vue'
import GUCCI from './components/GUCCI.vue'
import Yukina from './components/Yukina.vue'
import { defineComponent } from 'vue';
import V from './components/V.vue'

export default defineComponent({
  components: {
    // MyMap,
    Hiroki,
    GUCCI,
    Yukina,
    V
  },
  setup() {
    const tempo = ref(30);
    const draw_start = ref(false);
    const draw_stop = ref(false);
    const draw_reset = ref(false);
    // provide('tempo', 120)
    // provide('geolocation', {
    //   longitude: 90,
    //   latitude: 135
    // })
    provide('tempo',tempo)
    provide('draw_start',draw_start)
    provide('draw_stop',draw_stop)
    provide('draw_reset',draw_reset)
    return{
      
    }
  }
})
</script>

<template>
  <div class="all">
    <MyMap></MyMap>
    <div class="head">
      <div class="head_name">Umbrella Guitar</div>
      <div class="head_drag"><p>drag code and practice guitar</p></div>
    </div>
    <div class="nikai">
      <Yukina class="yuki"></Yukina>
      <div class="dansi">
        <Hiroki class="hiroki"></Hiroki>
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
 
  margin: 0%;
}

.gucchi {
  height: 80%;
}

.nikai {
  display: flex;
  width: 100%;
}

.dansi {
  width: 80%;
}
</style>
