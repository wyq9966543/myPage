<template>
    <div class="bilitop-box" ref="bilitop_box">
        <div :class="{head:!ifactive,active:ifactive}">
            <a class="logo">SkyLand</a>
            <ul class="top_ul">
                <li><a>动漫</a></li>
                <li><a>宅</a></li>
                <li><a>小说</a></li>
                <li><a>技术</a></li>
                <li><a>萌新</a></li>
                <li><a>二次元</a></li>
                <li><a>xixi</a></li>
            </ul>
        </div>
        <div class="bottom">
            <div class="text-box">
                <div class="text">
                    <h1>QwQ</h1>
                    <h3>仿阿b移动端的几个比较意思的小功能</h3>
                    <h3>1.下滑后上边导航栏样式改变，上滑到顶又恢复</h3>
                    <h3>2.选中导航栏某个选项后，多了下划线和不透明背景</h3>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    module.exports = {
        name: "my-component",
        data() {
            return {
                ifactive:false,
            }
        },
        mounted() {
            this.$refs.bilitop_box.addEventListener('scroll', this.handleScroll, true);
        },
        methods: {
            handleScroll() {
                // 页面滚动距顶部距离
                let scrollTop = this.$refs.bilitop_box.scrollTop;
                if(scrollTop!==0){
                    this.ifactive=true;
                }else{
                    this.ifactive=false;
                }
            }
        }
    }
</script>

<style scoped>
    *{
        margin: 0;
        padding: 0;
    }
    .bilitop-box {
        background: #1b181b;
        position: absolute;
        width: 100%;
        height:100%;
        overflow-y: scroll;
        overflow-x:hidden;
    }
    .bilitop-box::-webkit-scrollbar {
        /*滚动条整体样式*/
        width : 12px;  /*高宽分别对应横竖滚动条的尺寸*/
        height: 1px;
    }
    .bilitop-box::-webkit-scrollbar-thumb {
        /*滚动条里面小方块*/
        border-radius   : 10px;
        background-color: #ffffff;
    }
    .bilitop-box::-webkit-scrollbar-track {
        background   : #ffffff00;
    }
    .head{
        position:fixed;
        width:96%;
        display:flex;
        background: #1b181b80;
        align-items: center;
        padding:2%;
        color:#ffffff;
        font-weight: bold;
        transition: 0.5s ease-in-out;
        box-shadow:5px 5px 5px 5px #00000050;
        justify-content: space-between;
        overflow: hidden;
        z-index: 2;
    }
    .logo{
        position:relative;
        font-size:2em;
        user-select:none;
        cursor: pointer;
        transition: 0.5s ease-in-out;
        z-index: 2;
    }
    .logo:hover{
        letter-spacing: 5px;
    }
    .logo::after{
        content: '';
        position: absolute;
        top:0;
        left:0;
        width: 100%;
        height:100%;
        border-bottom: 2px solid #FFFFFF;
        transform: scale(1,1);
        opacity: 0;
        transition: 0.5s ease-in-out;
        z-index: 1;
    }
    .logo:hover::after{
        opacity: 1;
        transform:scale(1.3,2.2);
    }
    .logo::before{
        content: '';
        position: absolute;
        top:0;
        left:0;
        width: 100%;
        height:100%;
        transform: scale(1,1);
        opacity: 0;
        transition: 0.5s ease-in-out;
        background: #FFFFFF20;
        z-index: -1;
    }
    .logo:hover::before{
        opacity: 1;
        transform:scale(1.3,3);
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
    }
    .top_ul li a:before{
        content: '';
        position: absolute;
        top:0;
        left:0;
        width: 100%;
        height:100%;
        transform: scale(1,1);
        opacity: 0;
        transition: 0.5s ease-in-out;
        background: #FFFFFF20;
        z-index: -1;
    }
    .top_ul li a:hover:before {
        opacity: 1;
        transform:scale(1.3,3);
    }
    .top_ul li a:after{
        content: '';
        position: absolute;
        top:0;
        left:0;
        width: 100%;
        height:100%;
        border-bottom: 2px solid #FFFFFF;
        transform: scale(1,1);
        opacity: 0;
        transition: 0.5s ease-in-out;
        z-index: 1;
    }
    .top_ul li a:hover:after{
        opacity: 1;
        transform:scale(1.3,2.9);
    }
    .bottom{
        background: url("../assets/guanghui2.png");
        background-size: 100% auto;
        width: 100%;
        height: 120%;
    }
    .text-box{
        box-shadow:5px 5px 5px 5px #00000050;
        width: 500px;
        height:500px;
        position: fixed;
        top:20%;
        left:30%;
        background: #f441a5;
        padding-left: 0.5%;
        padding-top:0.5%;
        padding-bottom:0.5%;
        border-radius: 10px;
    }
    .text{
        user-select: none;
        cursor: pointer;
        height:100%;
        width:98.8%;
        background: #ffffff;
        border-radius: 10px;
        color:#f441a5;
    }
    .active{
        padding:0 2%;
        position:fixed;
        width:96%;
        display:flex;
        background: #ffffff;
        align-items: center;
        color:#000000;
        font-weight: bold;
        transition: 0.5s ease-in-out;
        box-shadow:5px 5px 5px 5px #00000050;
        justify-content: space-between;
        overflow: hidden;
        z-index: 2;
    }
    .active .top_ul li a:before{
        background: #00000010;
    }
    .active .logo:before{
        background: #00000010;
    }
    .active .top_ul li a:after{
        border-bottom: 5px solid #000000;
    }
    .active .top_ul li a:hover:after{
        opacity: 1;
        transform:scale(1.3,1);
    }
    .active .logo:after{
        border-bottom: 5px solid #000000;
    }
    .active .logo:hover:after{
        opacity: 1;
        transform:scale(1.3,0.8);
    }
</style>