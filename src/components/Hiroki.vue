<template>
	<div class = "hiroki">
	<div>It's me. This is Hiroki.</div>
	<canvas id = "can1" height="30"></canvas>
	</div>
</template>

<script setup lang="ts">import { withCtx } from 'vue';

	var canvas = document.getElementById("can1")

	var x = 20;
	var y = 20;
	var speed = 1;

</script>

<style>
	.hiroki{
		border: solid 1px pink;
	}
	canvas{
		border:solid 1px black;
		width: 50%;
	}
</style>