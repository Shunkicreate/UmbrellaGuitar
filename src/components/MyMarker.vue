<!-- src/components/MyMarker.vue -->

<template>
my marker
<div>{{userLocation}}</div>
<div>{{userGeolocation}}</div>
<div>{{updateUserLocation}}</div>
</template>

<script>
import { inject } from 'vue'

export default {
  setup() {
    const userLocation = inject('location', 'The Universe')
    const userGeolocation = inject('geolocation')
    const updateUserLocation = inject('updateLocation')

    return {
      userLocation,
      userGeolocation,
      updateUserLocation
    }
  }
}
</script>