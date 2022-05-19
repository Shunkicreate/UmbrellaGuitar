<!-- src/components/MyMap.vue -->
<template>
  <MyMarker></MyMarker>
  MyMap
  <button @click="change">スタート</button>
</template>

<script>
import { provide, reactive, ref } from 'vue'
import MyMarker from './MyMarker.vue'

export default {
  components: {
    MyMarker
  },
  setup() {
    const location = ref('North Pole')
    const geolocation = reactive({
      longitude: 90,
      latitude: 135
    })

    // const updateLocation = () => {
    //   location.value = 'South Pole'
    // }

    function change(){
        location.value = 'South PPPPPPPPPole'
    }

    provide('location', location)
    provide('geolocation', geolocation)
    // provide('updateLocation', updateLocation)

    return{
        change
    }
  }
}
</script>