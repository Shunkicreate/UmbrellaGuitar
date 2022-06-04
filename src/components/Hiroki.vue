<template>
	<!-- <div id="app"> -->
	<div class="hiroki">
		<button @click="test">test</button>
		<button @click="draw" :disabled="btn_lock1">スタート</button>
		<button @click="stop_draw" :disabled="btn_lock2">ストップ</button>
	</div>
	<div class="hiroki">
		<canvas id="can1" width="600" height="50"></canvas>
		<!-- <span v-if="true">speed{{num}}</span>
		<button @click="add_number">+</button>
		<button @click="sub_number" :disabled="btn_lock3">-</button> -->
	</div>
	<!-- </div> -->
</template>

<script lang="ts">
import { inject } from 'vue'
import { createApp, defineComponent, onMounted, VueElement, withCtx, ref, Ref } from 'vue';

export default defineComponent({
	name: "Hiroki",
	
	setup() {
		onMounted(() => {
		draw_set()
		});
		const tempo = inject('tempo', 120)
		let canvas: any;
		let ctx: any;
		var xstart = 600;
		var y = 15;
		const num:Ref<number> = ref(30);
		let speed = num.value/10;
		let change_count:boolean = true;
		const test_cont:Ref<boolean> = ref(false);

		const btn_lock1:Ref<boolean> = ref(false);
		const btn_lock2:Ref<boolean> = ref(true);
		const btn_lock3:Ref<boolean> = ref(false);
		const dwaw_start:Ref<boolean> = ref(false);

		function set_canvas(){
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

		function draw_set(){

			btn_lock1.value=false;
			btn_lock2.value=true;

			canvas = document.getElementById("can1");
			console.log(canvas);
			ctx = canvas.getContext('2d');
			console.log(ctx.fillStyle);
			ctx.fillStyle = "red";
			console.log(ctx.fillStyle);

			ctx.clearRect(0, 0, canvas.width, canvas.height);

			ctx.strokeRect(25, y, 20, 20)
			if (dwaw_start.value == true){
				var cnt = 0;
				var x = xstart + 100 * cnt;

				speed = tempo.value/10;

				for (var i = 0; i < 8; i++) {
					for (var j = 0; j < 4; j++) {
						ctx.fillRect(x, y, 20, 20);
						cnt++;
						x = xstart + 100 * cnt;
					}
				}

				xstart -= speed;

				if (xstart <= -1600) {
					xstart = 0;
					requestAnimationFrame(draw);
				}else if(xstart <= 600 && xstart > -1600){
					requestAnimationFrame(draw);
				}else{
					// stop
					btn_lock1.value = false;
					btn_lock2.value=true;
					xstart = 600;
				}
			}
		}
		

		function draw() {

			btn_lock1.value=true;
			btn_lock2.value=false;

			canvas = document.getElementById("can1");
			console.log(canvas);
			ctx = canvas.getContext('2d');
			console.log(ctx.fillStyle);
			ctx.fillStyle = "red";
			console.log(ctx.fillStyle);

			ctx.clearRect(0, 0, canvas.width, canvas.height);

			ctx.strokeRect(25, y, 20, 20)

			var cnt = 0;
			var x = xstart + 100 * cnt;

			speed = tempo.value/10;

			for (var i = 0; i < 8; i++) {
				for (var j = 0; j < 4; j++) {
					ctx.fillRect(x, y, 20, 20);
					cnt++;
					x = xstart + 100 * cnt;
				}
			}

			xstart -= speed;

			if (xstart <= -1600) {
				xstart = 0;
				requestAnimationFrame(draw);
			}else if(xstart <= 600 && xstart > -1600){
				requestAnimationFrame(draw);
			}else{
				// stop
				btn_lock1.value = false;
				btn_lock2.value=true;
				xstart = 600;
			}
		}

		function stop_draw(){
			xstart = 700;
		}

		function add_number(){
			num.value += 1;
			console.log(num);
			if(num.value == 1){
				btn_lock3.value=false;
			}
		}
		function sub_number(){
			num.value -= 1;
			console.log(num);
			if(num.value == 0){
				btn_lock3.value=true;
			}
		}
		function test(){
			if(test_cont.value == false){
				test_cont.value = true;
			}else{
				test_cont.value = false;
			}
		}
		return {
			draw,
			draw_set,
			tempo,
			y,
			num,
			btn_lock1,
			btn_lock2,
			btn_lock3,
			dwaw_start,
			test_cont,
			set_canvas,
			stop_draw,
			add_number,
			sub_number,
			test
		}
	},

	// if(test_cont.value == true){
	// 	draw()
	// }
});
</script>


<style>
#can1 {
	width: 97%;
}


canvas {
	box-shadow: 3px 3px 3px #a5aaabe5;
	padding: 1%;
}
</style>