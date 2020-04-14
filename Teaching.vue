<template>
<div class="wrap">

    <!--主导航-->
    <main-nav></main-nav>

    <!--主体-->
	<div class="main-box">
		
		<!--左侧-->
		<side-bar></side-bar>
		
		<!--右侧-->
		<div class="main-content">
			
			<!--轮播-->
			<div class="carousel-box">
				<el-carousel trigger="click" :interval="5000" height="100%">
					<el-carousel-item v-for="item in 4" :key="item">
						
						<section class="item">
							<figure><img src="../assets/images/book-over.png" /></figure>
							<span>
								<h1>春-朱自清教学方案</h1>
								<p><a class="open">打开课本</a><a class="enter">进入书架</a></p>
							</span>
						</section>
						
					</el-carousel-item>
				</el-carousel>
			</div>
			
			<!--授课资源-->
			<div class="book-assets">
				
				<section class="tab-box">
					<span class="tab">
						<el-radio-group v-model="radio" @change="changeType">
							<el-radio label="1">授课资源</el-radio>
							<el-radio label="2">备课资源</el-radio>
						</el-radio-group>
					</span>
					<template v-if="radio == 1"><span class="btn"><button>进入资源库</button></span></template>
					<template v-if="radio == 2"><span class="btn">当前章节：第一单元 - 春<button @click="changeChapter('Chapter')">切换章节</button></span></template>
				</section>
				
				<!--资源列表-->
				<component :is="panelName" :type="radio"></component>
				
			</div>

		</div>
		
	</div>

    <!--弹窗 b-->
    <popups></popups>
    <!--弹窗 e-->    

</div>
</template>


<script>
import MainNav from "@/components/MainNav"
import SideBar from "@/components//sk/SideBar"
import AssetsList1 from "@/components/sk/AssetsList1"
import AssetsList2 from "@/components/sk/AssetsList2"
import Popups from "@/components/Popups"

export default{
    name: 'Teaching',

    data() {
        return{

        	items: [],

			radio: '1',
			panelName: 'AssetsList1'

        }
    },

    components: {
        MainNav,
        SideBar,
        AssetsList1,
        AssetsList2,
        Popups
    }, 

    created() {       
    },

    methods: {
				
    	//切换资源
    	changeType(radio) {
    		return radio == 1 ? this.panelName = 'AssetsList1' : this.panelName = 'AssetsList2'
    	},

        //获取轮播课本
        getBook() {

            this.$axios.get('xxx',
                {
                    params: { 
                        xx: '',
                        xx: ''             
                    }
                })
                .then(res => {
                    this.items = res;

                })
                .catch(error => {
                    this.$message.error('请求失败，请重试！')          
                })      
        },

        //切换章节
        changeChapter(name) {
			this.$store.commit("showPop", {
				name: name,  //弹窗组件
				value: ''   //传参
			})	
        }
         
    }

}

</script>

<style lang="less" scoped>

/*变量*/
@blue: #4a95ff;           //蓝色（按钮类）
@tintBlue: #f0f5fb;      //浅蓝色背景
@bd: #c1dbff;           //浅蓝色边框
@f16: .16rem;          //字号
@f18: .18rem;         //字号

.main-box{
	flex: 1;
	display: flex;
	padding: 0 .4rem;
	margin-bottom: .3rem;
	overflow: hidden;
}


/*右侧*/
.main-content{
	flex: 1;
	display: flex;
	flex-flow: column;
	overflow: hidden
}

/*轮播*/ 
.carousel-box{
	flex: 0 0 3rem;
	overflow: hidden;
	border-radius: .04rem .04rem 0 0;
	background: url(../assets/images/banner-bg.png) no-repeat;
	background-size: cover;

	/deep/ .el-carousel{height: 100%;}
	/deep/ .el-carousel__arrow{width:.4rem;height:.4rem;background-color: rgba(0,0,0,.3)}
	/deep/ .el-carousel__arrow i{font-size: .18rem;}
	
	.item{
		height: 100%;
		display: flex;
		align-items: center;
		
		figure{
			flex: 0 0 1.59rem;
			height: 2.26rem;
			overflow: hidden;
			margin:0 .3rem 0 1.28rem;
			border-radius: .04rem;
			box-shadow: 0 0 .05rem .02rem rgba(0, 0, 0, 0.1);			
			img{width:100%}
		}
		
		h1{margin-bottom:.55rem;font-size: .24rem;font-weight: bold; color: #fff;text-shadow: 0 0 .02rem rgba(0,0,0,.7);}
		a{display:inline-block;width:1.35rem;line-height:.45rem;margin-right:.2rem;text-align:center;font-size:@f18;color:#fff;cursor:pointer;border-radius: .04rem;transition:background .4s 0s ease;}
		a.open{background: @blue;}
		a.enter{border:1px solid #fff;background:none;}
		a:hover{color:#fff !important;}
		a.open:hover{background: #1cba79;}
		a.enter:hover{background: #ff6a4d;}
	}
	
}
@media screen and (max-width:1400px){
	.carousel-box{flex: 0 0 3.5rem;}
}

/*授课资源*/
.book-assets{
	flex: 1;
	overflow: hidden;
	display: flex;
	flex-flow: column;
	padding: .2rem 0 .1rem;
	border-radius: 0 0 .04rem .04rem;
	border: 1px solid @bd;
	background: #fff;
}
.tab-box{
	flex: 0 0 .3rem;
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 0 .2rem;
	margin-bottom: .05rem;
}
.tab-box .tab{

	/deep/ .el-radio-group{
		display: flex;
		align-items: center;
	}
	
	/*定义radio样式*/
	/deep/ label{display:flex;align-items:center;margin-right:.4rem}
	/deep/ .el-radio__inner{width:.18rem;height:.18rem;}
	/deep/ .el-radio__inner::after{width:.1rem;height:.1rem;background:@blue;}
	/deep/ .el-radio__input.is-checked .el-radio__inner{border-color:@blue;background:#fff;}
	/deep/ .el-radio__label{padding-left:.1rem;font-weight:bold;font-size: @f18;color:#333}
}

.tab-box .btn{color:@blue}
.tab-box .btn button{
	width: 1rem;
	height: .3rem;
	margin-left: .2rem;
	color: #fff;
	border-radius: .02rem;
	background: #42c89d;
}

</style>
