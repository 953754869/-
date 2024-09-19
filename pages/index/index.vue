<template>
	<view class="g-content">
		<view class="main">
			<view class="header falc">
				<view style="flex: 1;">
					<image src="../../static/img/homeLogo2.jpg" mode="widthFix"></image>
				</view>
				<image src="../../static/img/homeLogo1.jpg" mode="widthFix"></image>
				<view class="inocbox falc">
					<view class="item falc">
						<uni-icons type="contact" size="80rpx" color='#616692'></uni-icons>
						我的
					</view>
					<view class="item falc">
						<uni-icons type="help" size="80rpx"color='#616692'></uni-icons>
						FAQ
					</view>
				</view>
			</view>
			<view class="navbox fcc">
				<view class="item" :class="navIndex===index?'active':''" v-for="(item,index) in navList">
					{{item}}
					<view v-if="navIndex===index&&index==1" class="jiantou fcc">
						<image src="../../static/img/jiantou.jpg" mode="widthFix" style="width: 60rpx;"></image>
					</view>
				</view>
				
			</view>
			<template v-if="navIndex==0">
				<view class="par2 fcc">
					<view class="leftbox swiper">
						<swiper :indicator-dots="false" autoplay style="height: 940rpx;" >
						  <swiper-item v-for="(item, index) in swiperList" :key="index">
							  <view class="item fcc">
								  <view class="imgbox">
									<image :src="item.img" class="slide-image" mode="scaleToFill"></image>
									<view class="title falc">
										{{item.title}}
									</view>
								  </view>
								  <view class="descbox">
									<view class="one">
										<view class="desc-title">
											{{item.title2}}
										</view>
										<view class="desc-word">
											{{item.cont2}}
										</view>
									</view>
									<view class="one">
										<view class="desc-title">
											{{item.title3}}
										</view>
										<view class="desc-word">
											{{item.cont3}}
										</view>
									</view>
								  </view>
								
							  </view>
						  </swiper-item>
						</swiper>
					</view>
					<view class="rightbox">
						<view class="descbox">
							<view class="desc-title">
								积分排行榜
							</view>
						</view>
						<view class="paihangbox">
							<view class="item" v-for="(item,index) in jifenList">
								<template v-if="index<3">
									<view class="icon" :class="`icon${index}`"></view>
								</template>
								<template v-else>
									<view class="iconNum fcc">
										{{index+1}}
									</view>
								</template>
								<image :src="item.src" class="slide-image" mode="scaleToFill"></image>
								<view>
									<view class="name">
										{{item.name}}
									</view>
									<view class="jifen">
										积分:{{item.jifen}}
									</view>
								</view>
							</view>
						</view>
					</view>
				</view>
				<view class="par3 fcc">
				<image src="../../static/img/homeTab1.jpg" mode="widthFix"></image>
				<image src="../../static/img/homeTab2.jpg" mode="widthFix"></image>
				<image src="../../static/img/homeTab3.jpg" mode="widthFix"></image>
				<image src="../../static/img/homeTab4.jpg" mode="widthFix"></image>	
			</view>
			</template>
			<template v-if="navIndex==1">
				<anquanguanliVue></anquanguanliVue>
			</template>
			<template v-if="navIndex==2">
				<anquandongtai></anquandongtai>
			</template>
		</view>
			
	</view>
</template>

<script>
	import anquanguanliVue from './comm/anquanguanli/anquanguanli.vue'
	import anquandongtai from './comm/anquandongtai/anquandongtai.vue'
	export default {
		components:{
			anquanguanliVue,
			anquandongtai
		},
		data() {
			return {
				navList:['首页','安全管理','安全动态','应知应会','警钟长鸣'],
				navIndex:2,
				jifenList:[
					{name:'11',jifen:'11',src:"https://q2.itc.cn/q_70/images03/20240904/14a2606879394c36a4d1cde4e98bbe1d.png"},
					{name:'22',jifen:'22',src:"https://q2.itc.cn/q_70/images03/20240904/14a2606879394c36a4d1cde4e98bbe1d.png"},
					{name:'33',jifen:'33',src:"https://q2.itc.cn/q_70/images03/20240904/14a2606879394c36a4d1cde4e98bbe1d.png"},
					{name:'44',jifen:'44',src:"https://q2.itc.cn/q_70/images03/20240904/14a2606879394c36a4d1cde4e98bbe1d.png"},
					{name:'55',jifen:'55',src:"https://q2.itc.cn/q_70/images03/20240904/14a2606879394c36a4d1cde4e98bbe1d.png"},
				],
				swiperList:[
					{
						img:'https://img95.699pic.com/photo/50694/7680.jpg_wh860.jpg',
						title:'title1',
						title2:'title2',
						cont2:'cont2',
						title3:'title3',
						cont3:'cont3',
					},
					{
						img:'https://tse1-mm.cn.bing.net/th/id/OIP-C.a0VLbBTM8-RJW8L4zRJ1aAHaE7?w=245&h=180&c=7&r=0&o=5&dpr=1.8&pid=1.7',
						title:'title1',
						title2:'title2',
						cont2:'cont2',
						title3:'title3',
						cont3:'cont3',
					}
				]
			}
		},
		methods: {

		}
	}
</script>

<style scoped lang="scss">
	.main{
		padding: 20rpx  80rpx 0;
	}
	.inocbox{
		.item{
			width: 170rpx;
			height: 80rpx;
			background-color: #353d83;
			color: #c5c7d6;
			border-radius: 80rpx;
			margin-left: 30rpx;
		}
	}
	.navbox{
		.item{
			color: #8c91b8;
			font-size: 50rpx;
			padding: 20rpx 40rpx;
			position: relative;
			margin: 0 30rpx;
			&.active{
				color: #e9f2fc;
				font-weight: bold;
				border-radius: 80rpx;
				background-color: #4070fd;
			}
			.jiantou{
				position: absolute;
				left: 0;
				right: 0;
				bottom: -60rpx;
				
			}
			
		}
		
	}
	.par2{
		padding: 30rpx 50rpx 0;
		height: 940rpx;
		.rightbox{
			width: 460rpx;
			border-radius: 10rpx;
			height: 940rpx;
			background-color: #3238A3;
			 background: linear-gradient(to bottom,  #3238A3, #3B53B2);
			margin-left: 40rpx;
			box-sizing: border-box;
			padding:42rpx 50rpx;
			.paihangbox{
				.item{
					margin:50rpx 0;
					display: flex;
					align-items: center;
					.slide-image{
						width:88rpx ;
						height: 88rpx;
						border-radius: 100%;
						margin:0 20rpx;
					}
					.name{
						font-size: 40rpx;
						color: #D6D7EC;
					}
					.jifen{
						font-size: 30rpx;
						color: #ADAFDA;
					}
					.iconNum{
						background-color: #5B5FB5;
						color: #BCBEE1;
						border-radius: 100%;
						width: 50rpx;
						height: 50rpx;
					}
					.icon{
						width: 50rpx;
						height: 60rpx;
						overflow: hidden;
						}
					.icon0{
						background-image: url("~@/static/img/homePaihang.jpg");
						background-size: 100%;
						background-repeat: no-repeat;
					}
					.icon1{
						background-image: url("~@/static/img/homePaihang.jpg");
						background-size: 100%;
						background-repeat: no-repeat;
						background-position:0px -140rpx;
					}
					.icon2{
						background-image: url("~@/static/img/homePaihang.jpg");
						background-size: 100%;
						background-repeat: no-repeat;
						background-position:0px -280rpx;
					}
				
				}
			}
			
	
		}
		.slide-image,.imgbox{
			width:1120rpx;
			height: 940rpx;
		}
		.swiper{
			border-radius: 10rpx;
			overflow: hidden;
			flex: 1;
			height: 940rpx;
		}
		.imgbox{
			position: relative;
			.title{
				position: absolute;
				bottom: 0px;
				height: 130rpx;
				background-color: #36343491;
				right: 0px;
				left: 0px;
				padding: 0 30rpx;
				color: #9D9FA9;
				font-size: 36rpx;
			}
		}
		.leftbox{
			.descbox{
				height: 940rpx;
				background-color: #282F97;
				flex: 1;
				padding:0rpx 60rpx;
				box-sizing: border-box;
				
			}
		}
		.descbox{
			.one{
				margin-top: 40rpx;
				padding-bottom: 20rpx;
			}
			.desc-title{
				color: #fff;
				font-weight: bold;
				font-size: 40rpx;
				position: relative;
				padding-left: 30rpx;
				border-bottom: 2rpx solid #7076B7;
				margin-bottom: 20rpx;
				padding-bottom: 20rpx;
				&:before{
					content: "";
					position: absolute;
					left: 0;
					background-color: #6E9FC7;
					width: 10rpx;
					top: 5rpx;
					height: 40rpx;
					border-radius: 20rpx;
					
				}
			
			}
			.desc-word{
				color: #A4A7CE;
				font-size: 32rpx;
			}
			
		}
		
	}
	.par3{
		
		image{
			width: 545rpx;
			margin: 60rpx 20rpx;
		}
	}
	

</style>
