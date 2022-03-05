<template>
<div>
this is Hiroki page
<div>{{counter}}</div>
<div><button @click="counter++">increase</button></div>
<div><button @click="counter--">decrease</button></div>
</div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const counter = ref(0)



</script>