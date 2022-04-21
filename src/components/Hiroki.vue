<template>
	<!-- <div id="app"> -->
	<div class="hiroki">
		<div>It's me. This is Hiroki.</div>
		<button @click="draw">スタート</button>
		<canvas id="can1" width="600" height="50"></canvas>
		<!-- <span>test{{ y }}</span> -->
		<span v-if="true">count is {{number}}</span>
		<button @click="add_number">+</button>
		<button @click="sub_number">-</button>
	</div>
	<!-- </div> -->
</template>

<script lang="ts">
import { createApp, defineComponent, onMounted, VueElement, withCtx } from 'vue';
// import AppVue from '../App.vue';


export default defineComponent({
	name: "Hiroki",
	setup() {
		// onMounted(()=>{
		let canvas: any;
		let ctx: any;
		var xstart = 600;
		var y = 15;
		var speed = 3;
		let change_count:boolean = true;

		let number = 0;

		function draw() {

			// document.addEventListener('DOMContentLoaded',(Event)=>{
			// canvas = <HTMLCanvasElement>document.getElementById("can1");
			canvas = document.getElementById("can1");
			console.log(canvas);
			ctx = canvas.getContext('2d');
			console.log(ctx.fillStyle);
			ctx.fillStyle = "red";
			console.log(ctx.fillStyle);



			// requestAnimationFrame(draw);

			ctx.clearRect(0, 0, canvas.width, canvas.height);

			ctx.strokeRect(25, y, 20, 20)

			var cnt = 0;
			var x = xstart + 100 * cnt;

			for (var i = 0; i < 2; i++) {
				for (var j = 0; j < 4; j++) {
					ctx.fillRect(x, y, 20, 20);
					cnt++;
					x = xstart + 100 * cnt;
				}
			}

			xstart -= speed;

			if (xstart > -1000) {
				requestAnimationFrame(draw);
			}
		}
		function add_number(){
			number += 1;
			console.log(number);
		}
		function sub_number(){
			number -= 1;
			console.log(number);
		}
		return {
			draw,
			y,
			number,
			add_number,
			sub_number,
		}
		// })
	}
});


</script>


<style>
.hiroki {
	border: solid 1px pink;
}

canvas {
	border: solid 1px black;
}
</style>