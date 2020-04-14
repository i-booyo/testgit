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
			
			<div class="content-top">
				<span class="left"><i class="iconfont icon-mulu"></i>春</span>
				<span class="right">
					<button @click='chooseFiles'><i class="home"></i>添加本地资源</button>
					<input type="file" ref='importFiles' @change='importFiles($event)' style="display:none" />
					<button @click="addCloudAsset('CloudAssetPop')"><i class="cloud"></i>添加云端资源</button>
				</span>
			</div>
			
			<!--列表-->
			<div class="list-box">
				<div class="scroll-view">
					
					<ul>
						<li>
							<h4><img src="../assets/images/fileicon/ppt.png" />【教学方案】春-朱自清教学方案.pptx</h4>
							<span class="date">2020-03-17</span>
							<span class="operation">
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="下载资源" placement="top"><i class="iconfont icon-tobottom"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="分享资源" placement="top"><i class="iconfont icon-share2" @click="share('Share',1)"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="删除记录" placement="top"><i class="iconfont icon-remove4" @click="deleteItem('Delete',1)"></i></el-tooltip>
							</span>
						</li>
						<li>
							<h4><img src="../assets/images/fileicon/photo.png" />【教学方案】春-朱自清教学方案.jpg</h4>
							<span class="date">2020-03-17</span>
							<span class="operation">
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="下载资源" placement="top"><i class="iconfont icon-tobottom"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="分享资源" placement="top"><i class="iconfont icon-share2" @click="share('Share',2)"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="删除记录" placement="top"><i class="iconfont icon-remove4" @click="deleteItem('Delete',2)"></i></el-tooltip>
							</span>
						</li>
						<li>
							<h4><img src="../assets/images/fileicon/word.png" />【教学方案】春-朱自清教学方案.doc</h4>
							<span class="date">2020-03-17</span>
							<span class="operation">
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="下载资源" placement="top"><i class="iconfont icon-tobottom"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="分享资源" placement="top"><i class="iconfont icon-share2" @click="share('Share',3)"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="删除记录" placement="top"><i class="iconfont icon-remove4" @click="deleteItem('Delete',3)"></i></el-tooltip>
							</span>
						</li>
						<li>
							<h4><img src="../assets/images/fileicon/ppt.png" />【教学方案】春-朱自清教学方案.pptx</h4>
							<span class="date">2020-03-17</span>
							<span class="operation">
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="下载资源" placement="top"><i class="iconfont icon-tobottom"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="分享资源" placement="top"><i class="iconfont icon-share2" @click="share('Share',1)"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="删除记录" placement="top"><i class="iconfont icon-remove4" @click="deleteItem('Delete',1)"></i></el-tooltip>
							</span>
						</li>
						<li>
							<h4><img src="../assets/images/fileicon/photo.png" />【教学方案】春-朱自清教学方案.jpg</h4>
							<span class="date">2020-03-17</span>
							<span class="operation">
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="下载资源" placement="top"><i class="iconfont icon-tobottom"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="分享资源" placement="top"><i class="iconfont icon-share2" @click="share('Share',2)"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="删除记录" placement="top"><i class="iconfont icon-remove4" @click="deleteItem('Delete',2)"></i></el-tooltip>
							</span>
						</li>
						<li>
							<h4><img src="../assets/images/fileicon/word.png" />【教学方案】春-朱自清教学方案.doc</h4>
							<span class="date">2020-03-17</span>
							<span class="operation">
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="下载资源" placement="top"><i class="iconfont icon-tobottom"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="分享资源" placement="top"><i class="iconfont icon-share2" @click="share('Share',3)"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="删除记录" placement="top"><i class="iconfont icon-remove4" @click="deleteItem('Delete',3)"></i></el-tooltip>
							</span>
						</li>
						<li>
							<h4><img src="../assets/images/fileicon/ppt.png" />【教学方案】春-朱自清教学方案.pptx</h4>
							<span class="date">2020-03-17</span>
							<span class="operation">
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="下载资源" placement="top"><i class="iconfont icon-tobottom"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="分享资源" placement="top"><i class="iconfont icon-share2" @click="share('Share',1)"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="删除记录" placement="top"><i class="iconfont icon-remove4" @click="deleteItem('Delete',1)"></i></el-tooltip>
							</span>
						</li>
						<li>
							<h4><img src="../assets/images/fileicon/photo.png" />【教学方案】春-朱自清教学方案.jpg</h4>
							<span class="date">2020-03-17</span>
							<span class="operation">
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="下载资源" placement="top"><i class="iconfont icon-tobottom"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="分享资源" placement="top"><i class="iconfont icon-share2" @click="share('Share',2)"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="删除记录" placement="top"><i class="iconfont icon-remove4" @click="deleteItem('Delete',2)"></i></el-tooltip>
							</span>
						</li>
						<li>
							<h4><img src="../assets/images/fileicon/word.png" />【教学方案】春-朱自清教学方案.doc</h4>
							<span class="date">2020-03-17</span>
							<span class="operation">
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="下载资源" placement="top"><i class="iconfont icon-tobottom"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="分享资源" placement="top"><i class="iconfont icon-share2" @click="share('Share',3)"></i></el-tooltip>
								<el-tooltip popper-class="tooltip" :open-delay="500" effect="dark" content="删除记录" placement="top"><i class="iconfont icon-remove4" @click="deleteItem('Delete',3)"></i></el-tooltip>
							</span>
						</li>						
					</ul>

					<!--暂无数据-->
					<data-null tipsText="本节课您还没有备课资源哦~" v-if="isNull"></data-null>
										
				</div>
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
import SideBar from "@/components/bk/SideBar"
import Popups from "@/components/Popups"
import DataNull from "@/components/DataNull"

export default{
    name: 'Prepare',

    data() {
        return{
			
			isNull: false,

            loading: false
        }
    },

    components: {
        MainNav,
        SideBar,
        Popups,
		DataNull
    }, 

    created() {  
    },

    methods: {
             
		//导入本地资源
		chooseFiles() {
			this.$refs.importFiles.click();
		},	
		
		importFiles(e) {
			let fileObj = e.target.files[0];       //文件对象
			let name = fileObj.name;               //文件名称
			let typeName = name.split('.').pop();  //获取文件后缀	
			
			//判断文件格式
			let fileTpye= /(jpg|jpeg|png|gif)$/;  //设置文件格式限制
			if(!fileTpye.test(typeName)){				
				this.$message.error('不支持的文件格式，请重新选择！');
				return false;
			}
			
		},
				
		//添加云端资源弹窗
        addCloudAsset(name) {   
			this.$store.commit("showPop", {
				name: name,  //弹窗组件
				value: ''   //传参
			})		
        },
		
		//重命名
        rename(name,id) {   
			this.$store.commit("showPop", {
				name: name,  //弹窗组件
				value: id   //传参
			})		
        },
		
		//重命名
        share(name,id) {   
			this.$store.commit("showPop", {
				name: name,  //弹窗组件
				value: id   //传参
			})		
        },
				
		//删除
        deleteItem(name,id) {   
			this.$store.commit("showPop", {
				name: name,  //弹窗组件
				value: id   //传参
			})		
        }		
		

    }

}

</script>

<style lang="less" scoped>

/*变量*/
@blue: #4a95ff;          //蓝色（按钮类）
@tintBlue: #f0f5fb;     //浅蓝色背景
@bd: #c1dbff;          //浅蓝色边框
@f16: .16rem;         //字号
@f18: .18rem;         //字号

.main-box{
	flex: 1;
	display: flex;
	overflow: hidden;
}

/*右侧*/ 
.main-content{
	flex: 1;
	display: flex;
	flex-flow: column;
	border-radius: .04rem 0 0 0;
	border-left: 1px solid @bd;
	border-top: 1px solid @bd;
	background: #fff;
}

.content-top{
	flex: 0 0 .6rem;
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 0 .2rem;
	border-bottom: 1px solid @bd;
	
	.left{
		font-size: .16rem;
		i{margin-right:.1rem;color:#5d6772}
	}
	.right{display: flex;}
	button{
		display: flex;
		align-items: center;
		height: .36rem;
		padding: 0 .15rem;
		color: #fff;
		margin-left: .1rem;
		border-radius: .03rem;
		background: @blue;
		transition: opacity .4s 0s ease;
			
		i{width:.2rem;height:.15rem;margin-right:.08rem;}
		i.home{background: url(../assets/images/home2.png) center center no-repeat;background-size: 100%;}
		i.cloud{background: url(../assets/images/cloud2.png) center center no-repeat;background-size: 100%;}
	}
	
}

.list-box{
	flex: 1;
	padding: 0 0 .2rem;
	overflow: hidden;
}
.scroll-view{
	height: 100%;
	padding: 0 .2rem;
	overflow-y: auto;
	
	section{margin-bottom: .2rem;border: 1px solid #eee;}
	h3{
		display: flex;
		align-items: center;
		height: .4rem;
		padding: 0 .2rem;
		font-size: @f16;
		background: @tintBlue;
		
		i{width: .2rem;height: .15rem;margin-right: .08rem;}
		i.home{background:url(../assets/images/home.png) center center no-repeat;background-size: 100%;}
		i.cloud{background:url(../assets/images/cloud.png) center center no-repeat;background-size: 100%;}
	}
	ul{	
		li{display: flex;justify-content:space-between;align-items:center;height: .84rem;padding: 0 .2rem;border-bottom: 1px solid #eee;}
		li:last-child{border:none;}
		h4{
			flex: 1;
			display: flex;
			align-items: center;
			font-size: @f16;
			img{flex:0 0 .34rem;height:.34rem;margin-right:.15rem;}
		}
		.date{margin:0 .5rem 0 .2rem;color:#999}
		.operation{
			color: @blue;
			i{margin-left:.25rem;cursor:pointer;transition:color .4s 0s ease;}
			i:hover{color:#bbc1c8;}		
		}		
	}
}

</style>
<style>
/*自定义toolTips样式*/
.tooltip{font-size:14px!important;background:rgba(0,0,0,.8) !important;}
.tooltip.el-tooltip__popper[x-placement^="top"] .popper__arrow{border-top-color:rgba(0,0,0,.8)}
.tooltip.el-tooltip__popper[x-placement^="top"] .popper__arrow:after{border-top-color:rgba(0,0,0,.8)}	
</style>
