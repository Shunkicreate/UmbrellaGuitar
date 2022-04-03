<template>
	<div class = "hiroki">
	<div>It's me. This is Hiroki.</div>
	<canvas id ="can1" width="600" height="50"></canvas>
	</div>
</template>

<script setup lang="ts">
	import { withCtx } from 'vue';

	let canvas:any;
	let ctx:any;

	document.addEventListener('DOMContentLoaded',(Event)=>{
		canvas = <HTMLCanvasElement>document.getElementById("can1");
		// console.log(canvas);
		ctx = canvas.getContext('2d');
		console.log(ctx.fillStyle);
		ctx.fillStyle="red";
		console.log(ctx.fillStyle);

		var xstart = 600;
		var y = 15;
		var speed = 3;

		draw();

		function draw(){
			requestAnimationFrame(draw);

			ctx.clearRect(0,0,canvas.width,canvas.height);

			ctx.strokeRect(25,y,20,20)

			var cnt = 0;
			var x = xstart + 100 * cnt;

			for(var i = 0;i < 2; i++){
				for(var j = 0; j < 4; j++){
					ctx.fillRect(x,y,20,20);
					cnt++;
					x = xstart + 100 * cnt;
				}
			}

			xstart -= speed;
		}
	});

	// ctx.fillstyle="pink"


	// var speed = 1;
	// ctx?.fillStyle = "pink";

	// function draw(){
	// 	ctx.clearRect(0,0,canvas.width,canvas.height);
	// 	ctx.fillRect(x,y,20,20)

		
	// 	// ctx.clearRect(0,0,canvas.width,canvas.height);
	// 	// ctx.fillRect(x,y,20,20);

	// 	x += speed;
	// 	requestAnimationFrame(draw);
	// }

	// draw();

</script>

<style>
	.hiroki{
		border: solid 1px pink;
	}
	canvas{
		border:solid 1px black;
	}
</style>