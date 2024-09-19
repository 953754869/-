<template>
	<view class="anquandongtai">
		<view class="main fcc">
			<view class="leftbox">
				<view class="titlebox">
					<view class="titleIcon"></view>
					企业动态
				</view>
				<view class="item" :class="navActive == index?'active':''" v-for="(item, index) in navList">
					{{item}}
				</view>
			</view>
			<view class="rightbox">
				<view class="top">
					查看全部 >>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				navList:['二级分类','二级分类','二级分类','二级分类','二级分类'],
				navActive:0
			};
		}
	}
</script>

<style lang="scss">
.anquandongtai{
	.main{
		border-radius: 20rpx;
		height: 1200rpx;
		margin-top: 40rpx;
		background: linear-gradient(to right,  #3238A3, #395BB5);
	}
	.rightbox{
		flex: 1;
		height: 1200rpx;
		padding: 0 80rpx;
		.top{
			font-size: 36rpx;
			color: #888ECC;
			font-weight: bold;
			line-height: 130rpx;
			text-align: right;
		}
	}
	.leftbox{
		padding:  50rpx 0 0 60rpx;
		height: 1200rpx;
		width: 560rpx;
		color: #fff;
		position: relative;
		&:before{
			position: absolute;
			content: '';
			background: linear-gradient(to bottom, rgba(255, 255, 255, 0), #9295CE 20%, rgba(255, 255, 255, 0));
			top: 0;
			bottom: 0;
			right: 0;
			width: 2rpx;
		}
		.item{
			font-size: 36rpx;
			line-height: 100rpx;
			padding-left: 60rpx;
			&.active{
				background: linear-gradient(to right, #3137A2, #3954CF);
				border-right: 6rpx solid #4070FD;
			}
			
		}
		.titlebox{
			display: flex;
			margin-bottom: 30rpx;
			align-items: center;
			font-size: 45rpx;
			color: #fff;
			font-weight: bold;
			.titleIcon{
				height: 60rpx;
				margin-right: 20rpx;
			}
		}
		
	}
	
}

</style>
