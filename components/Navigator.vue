<template>
	<div class="wrapper" ref='N'>
		<div :class="ifactive ? 'active' : 'navigator'">
			<a class="logo" v-if="ifactive">
				<img src="https://i0.hdslb.com/bfs/face/1d98dd717ead5a3178dcecf4bcc1ec29037895bf.jpg@48w_48h_100Q_1c.webp" alt="雨落天满星">
				<span>雨落天满星</span>
			</a>
			<ul class="top_ul">
				<li v-for="(item, index) in items" :key='index'>
					<a>{{item}}</a>
				</li>
			</ul>
		</div>
	</div>
	
</template>

<script>
	module.exports = {
		name: "Navigator",
		data() {
		    return {
				items: ['主页', '图片墙','点赞','收藏'],
		        ifactive: false,
				top: 0
		    }
		},
		mounted() {
			this.GetTop()
			window.addEventListener('scroll', this.handleScroll, true)
		},
		methods: {
			GetTop() {
				this.top = this.$refs.N.offsetTop+this.$refs.N.offsetHeight
				console.log(this.top)
			},
		    handleScroll() {
				let scrollTop = document.body.scrollTop || 
								window.pageYOffset || 
								document.documentElement.scrollTop
								// document.querySelector(this.el).scrollTop
				console.log(scrollTop)
		        if(scrollTop < this.top){
		            this.ifactive = false
		        }else{
					this.ifactive = true
		        }
		    }
		},
	}
</script>

<style>
	.navigator {
		position:relative;
		width:100%;
		display:flex;
		align-items: center;
		justify-content: flex-start;
		padding: 0.7em 0;
		font-weight: bold;
		background: #fff;
		box-shadow: 0 0 0 1px #eee;
		border-radius: 0 0 4px 4px;
		overflow: hidden;
		z-index: 2;
		transition: 0.5s ease-in-out;
	}
	
	.logo {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	
	.logo img{
		width: 30px;
		padding: 0 10px;
		border-radius: 50%;
	}
			
	.top_ul{
		position: relative;
		display:flex;
		font-size: 1.5em;
		list-style: none;
		user-select:none;
		cursor: pointer;
		transition: 0.5s ease-in-out;
		z-index: 2;
	}
	
	.top_ul li a{
		position: relative;
		display: block;
		margin:0 20px;
		transition: 0.5s ease-in-out;
	}
	.top_ul li a:hover{
		letter-spacing:5px;
		color: #00a1d6;
	}
	
	.top_ul li a:after{
		content: '';
		position: absolute;
		top:0;
		left:0;
		width: 100%;
		height:100%;
		border-bottom: 0.1em solid #00a1d6;
		transform: scale(1,1);
		opacity: 0;
		transition: 0.5s ease-in-out;
		z-index: 1;
	}
	.top_ul li a:hover:after{
		opacity: 1;
		transform:scale(1.3,1.4);
	}
	
	.active {
	    position: fixed;
		top: 0;
		left: 0;
		width: 100%;
	    display:flex;
	    background: #ffffff;
		padding: 0.7em 0;
	    align-items: center;
	    color:#000000;
	    font-weight: bold;
		transform: translateY(-90%) ;
	    transition: 0.5s ease-in-out;
		border-radius: 0 0 4px 4px;
	    box-shadow:0 0 0 3px #00000050;
	    justify-content: flex-start;
	    overflow: hidden;
	    z-index: 2;
	}
	
	.active:hover {
		transform: translateY(0) ;
		transition: 0.5s ease-in-out;
	}
	
</style>
