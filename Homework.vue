<template>
<div class="wrap">

    <!--主导航-->
    <main-nav></main-nav>

    <!--主体-->
	<div class="main-box">
		<div class="item-list">
			<section><img src="../assets/images/hw_ico1.png" /><strong>布置作业</strong></section>
			<section><img src="../assets/images/hw_ico2.png" /><strong>批改作业</strong><mark>未批改：20</mark></section>
			<section><img src="../assets/images/hw_ico3.png" /><strong>作业分析</strong></section>
		</div>
		<div class="item-list">
			<section><img src="../assets/images/hw_ico4.png" /><strong>师生互动</strong><mark>未读消息：15</mark></section>
			<section><img src="../assets/images/hw_ico5.png" /><strong>统计报告</strong></section>
			<section><img src="../assets/images/hw_ico6.png" /><strong>错题本</strong></section>		
		</div>
	</div>

    <!--弹窗 b-->
    <popups></popups>
    <!--弹窗 e-->

</div>
</template>

<script>
import MainNav from "@/components/MainNav"
import Popups from "@/components/Popups"

export default{
    name: 'Homework',

    data() {
        return{

            loading: false

        }
    },

    components: {
        MainNav,
        Popups
    }, 

    created() {       
    },

    methods: {

        //获取数据
        getXXXX() {

            this.$axios.get('xxx',
                {
                    params: { 
                        xx: '',
                        xx: ''             
                    }
                })
                .then(res => {

                })
                .catch(error => {
                    this.$message.error('请求失败，请重试！')          
                })      
        },


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
	flex-flow: column;
	padding: .69rem .5rem 0;
	margin-bottom: .2rem;
	overflow-y: auto;
}
.item-list{
	flex: 0 0 auto;
	display: flex;
	justify-content: space-between;
}
.item-list:first-child{margin-bottom: .2rem;}
section{
	display: flex;
	align-items: center;
	width: 4.2rem;
	height: 2rem;
	overflow: hidden;
	padding: 0 .5rem;
	margin-right: .2rem;
	font-size: @f18;
	color: #5d6772;
	position: relative;
	cursor: pointer;
	border-radius: .06rem;
	border: 1px solid @bd;
	background: #fff;
	transition: box-shadow .4s 0s ease;
	
	img{width:1.02rem;margin-right: .18rem;}
	mark{
		width: 1.1rem;
		line-height: .32rem;
		font-size: .14rem;
		text-align: center;
		color: #fff;
		white-space: nowrap;
		position: absolute;
		right: 0;
		top: 0;
		border-radius: 0 0 0 .06rem;
		background: #42c89d;
	}
}
section:hover{
	box-shadow: 0 0 .1rem .02rem rgba(0, 0, 0, 0.08);
}
section:last-child{margin:0;}

</style>
