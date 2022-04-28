<template>
	<!-- <div id="app"> -->
	<div class="hiroki">
		<div>It's me. This is Hiroki.</div>
		<button @click="draw" :disabled="btn_lock1">スタート</button>
		<button @click="stop_draw">リセット</button>
		<canvas id="can1" width="600" height="50"></canvas>
		<!-- <span>test{{ y }}</span> -->
		<span v-if="true">count is {{num}}</span>
		<button @click="add_number">+</button>
		<button @click="sub_number">-</button>
	</div>
	<!-- </div> -->
</template>

<script lang="ts">
import { createApp, defineComponent, onMounted, VueElement, withCtx, ref, Ref } from 'vue';
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
		// let btn_lock1:boolean = false;

		const num:Ref<number> = ref(0);
		const btn_lock1:Ref<boolean> = ref(false);

		function set_canvas(){
			// document.addEventListener('DOMContentLoaded',(Event)=>{
				console.log("this is set_canvas");
				canvas = document.getElementById("can1");
				console.log(canvas);
				ctx = canvas.getContext('2d');
				console.log(ctx.fillStyle);
				ctx.fillStyle = "red";
				console.log(ctx.fillStyle);
				ctx.clearRect(0, 0, canvas.width, canvas.height);

				ctx.strokeRect(25, y, 20, 20)
				
		}
		
		// set_canvas()

		function draw() {

			// document.addEventListener('DOMContentLoaded',(Event)=>{
			// canvas = <HTMLCanvasElement>document.getElementById("can1");
			btn_lock1.value=true;

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
				// btn_lock1.value=true;
			}else{
				xstart = 600;
				btn_lock1.value=false;
			}
		}

		function stop_draw(){
			xstart = -1500;
		}

		function add_number(){
			num.value += 1;
			console.log(num);
		}
		function sub_number(){
			num.value -= 1;
			console.log(num);
		}
		return {
			draw,
			y,
			num,
			btn_lock1,
			set_canvas,
			stop_draw,
			add_number,
			sub_number,
		}
		// draw();
		// })
	},
		

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