<template>
	<view class="anquanguanli">
		<view class="main fcc">
			<view class="item" v-for="(item,index) in navList">
				<view class="name fcc">
					{{item}}
				</view>
				<view class="gradient-s"></view>
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				navList:['领导指示','法律法规','企业制度','企业动态']
			};
		}
	}
</script>

<style lang="scss">
.anquanguanli{
	.main{
		width: 2040rpx;
		margin:60rpx auto;
		overflow: hidden;
		border-radius: 10rpx;
		height: 200rpx;
		background: linear-gradient(to right,  #3238A3, #395BB5);
		
	}
	.item{
		display: flex;
		position: relative;
		font-size: 40rpx;
		font-weight: bold;
		width: 25%;
		&:last-child{
		 .gradient-s{display: none;}	
		}
		.gradient-s{
			height: 140rpx;
		}
		.name{
			flex: 1;
		}
		
	}
	 
}

</style>
