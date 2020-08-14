<template>
	<div class="wrapper">
		<div class="masonry">
			<div class="item" v-for="(img,index) in 50" :key='index'>
				<div class="item-content">
					<img :src=`https://picsum.photos/${getRandon()}/${getRandon()+50}?random=${img}` alt=""/>
				</div>
			</div>
		</div>
	</div>
	
</template>

<script>
	module.exports = {
		name: "imgpage",
		methods: {
			getRandon() {
				let num = Math.random()
				num = num * 100+250
				num = Math.floor(num)
				// console.log(num)
				return num
			}
			
		},
	}
</script>

<style>
	.masonry {
		margin-top: 5px;
		column-count: 4;
		column-gap: 0;
	}
	
	.item {
		padding: 8px;
	}
	
	.item-content {
		position: relative;
		width: 100%;
		height: 100%;
		border-radius: 16px;
		overflow: hidden
	}
	
	.item img{
		display: block;
		width: 100%;
		height: auto;
		border-radius: calc(16px);
	}
	
	.item img:hover{
		width: 100%;
		height: auto;
		transform: scale(1.5,1.5);
		transition: opacity .3s,transform .3s ease,-webkit-transform .3s ease;
	}
</style>

