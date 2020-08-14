<template>
	<div class="h">
		<div class="wrapper">
			<div class="h-inner" style="background-image: url(https://i0.hdslb.com/bfs/space/cb1c3ef50e22b6096fde67febe863494caefebad.png@2200w_400h_1o.webp);">
				<div class="h-gradient"></div>
				<div class="h-user">
					<div class="h-info clearfix">
						<div class="h-avatar">
							<img src="https://i0.hdslb.com/bfs/face/1d98dd717ead5a3178dcecf4bcc1ec29037895bf.jpg@78w_79h_1c_100q.webp"
							 id="h-avatar">
							 <a target="_blank" class="avatar-cover">更换头像</a>
							 <span class="user-auth-subscript avatar-m"></span>
						</div>
						<div class="h-basic">
							<div>
								<span id="h-name">雨落天满星</span><span id="h-ceritification" class="icon"></span>
							</div>
							<div class="h-basic-spacing">
								<h4 title="" class="h-sign" style="display: none;"></h4>
								<input id="h-sign" type="text" placeholder="编辑个性签名" maxlength="60" class="space_input">
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	module.exports = {
		name: "H"
	}
</script>

<style>
	
	.h {
	    position: relative;
	    z-index: 10
	}
	
	.h .h-inner {
	    background-image: url(https://i0.hdslb.com/bfs/space/cb1c3ef50e22b6096fde67febe863494caefebad.png@2200w_400h_1o.webp);
	    background-position: 50%;
	    background-size: cover;
	    transition: background-image .2s ease,background-size 1s ease;
	    padding-top: 116px;
	    position: relative
	}
	
	.h .h-user {
	    position: relative;
	    z-index: 1
	}
	
	.h .h-gradient {
	    position: absolute;
	    bottom: 0;
	    left: 0;
	    width: 100%;
	    height: 84px;
	    background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABQAAAABdCAMAAADNEjtLAAABEVBMVEUDAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAAADAACnjvHuAAAAW3RSTlMBAgMEBQYHCAkKCwwNDxAREhQVFhgZGxweHyEiJCUnKSosLS8xMjQ2ODk7PT5AQkNFR0hKTE5PUVNUVldZW1xeX2FiZGVnaGprbG5vcHFzdHV2d3h5ent8fX5/XoZ4lgAAAPVJREFUeAHt1AERADAQAiDdrX/mDyKEIAAAjGkDsOk3AAIEECCAAAEECCBAAAECCBBAgAACBBAggAABBAggQAABAggQQIAAAgQQIIAAAQQIIEAAAQIIEECAAAIEECCAAAEECAgQQIAAAgQQIIAAAQQIIEAAAQIIEECAAAIEECCAAAEECCBAAAECCBBAgAACBBAggAABBAggQAABAggQQIAAAgQQIIAAAQECCBBAgAACBBAggAABBAggQAABAggQQIAAAgQQIIAAAQQIIEAAAQIIEECAAAIEECCAAAEECCBAAAECCBBAgAACBAQIIEAAAQIseAEYdZ9sAcJDX4ICAAAAAElFTkSuQmCC);
	    background-repeat: repeat-x
	}
	
	.h .h-avatar {
	    position: relative;
	    float: left;
	    width: 64px;
	    height: 64px;
	    border: 2px solid hsla(0,0%,100%,.4);
	    border-radius: 52px
	}
	
	.h .h-avatar:hover .avatar-cover {
	    opacity: 1
	}
	
	.h .h-avatar .avatar-cover {
	    position: absolute;
	    top: 0;
	    left: 0;
	    width: 64px;
	    height: 64px;
	    background: rgba(0,0,0,.6);
	    font-size: 12px;
	    color: #fff;
	    line-height: 64px;
		text-decoration: none;
	    text-align: center;
	    opacity: 0;
	    border-radius: 50%;
	    transition: opacity .2s
	}
	
	.h #h-avatar {
	    width: 64px;
	    height: 64px;
	    background: #fff;
	    border-radius: 48px
	}
	
	.h .h-info {
	    margin-left: 20px;
	    padding-bottom: 16px
	}
	
	.clearfix:after {
		content: '\20';
		display: block;
		height: 0;
		clear: both;
	}
	
	.h .h-basic {
	    float: left;
	    color: #fff;
	    font-size: 0;
	    margin: 10px 0 0 20px
	}
	
	.h .h-basic .h-basic-spacing {
	    margin-top: 8px
	}
	
	.h #h-sign {
	    background: transparent;
	    border-radius: 4px;
	    border: none;
	    box-shadow: none;
	    color: #d6dee4;
	    font-size: 12px;
	    font-family: Microsoft Yahei;
	    line-height: 26px;
	    height: 26px;
		width: 740px;
	    margin-left: -5px;
	    padding: 0 5px;
	    position: relative;
	    top: -1px;
	}
	
	.h #h-sign:hover {
	    background: hsla(0,0%,100%,.2);
	    box-shadow: 0 0 0 1px hsla(0,0%,100%,.5)
	}
	
	.h #h-sign:focus {
	    background: #fff;
	    box-shadow: inset 0 2px 4px rgba(35,54,86,.3);
	    color: #6d757a
	}
	
	.h #h-sign::-webkit-input-placeholder {
	    color: #d6dee4
	}
	
	.h #h-sign:-moz-placeholder,.h #h-sign::-moz-placeholder {
	    color: #d6dee4
	}
	
	.h #h-sign:-ms-input-placeholder {
	    color: #d6dee4
	}
	
	.space_input {
	    line-height: 28px;
	    height: 28px;
	    padding: 0 10px;
	    transition: all .3s ease;
	    vertical-align: top;
	    border: 1px solid #ccd0d7;
	    border-radius: 0;
	}
	
	.h #h-name {
	    display: inline-block;
	    margin-right: 5px;
	    font-weight: 700;
	    line-height: 18px;
	    font-size: 18px;
	    vertical-align: middle
	}
</style>
