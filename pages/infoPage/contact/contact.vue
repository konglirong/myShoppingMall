<template>
	<view class="content">
		<image src="../../../static/swipper/img1.jpg" class="imageStyle"></image>
		<view class="info">
			<view class="phone" @click="phone">联系电话：15629085742（点击拨打）</view>
			<view class="address">
				联系地址：武汉市洪山区光谷时代广场
			</view>
		</view>
		<map class="map" :scale="scale" :longitude="longitude" :latitude="latitude" :markers="mark"></map>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// 114.420857,30.507331
				longitude:114.420857,
				latitude:30.50733,
				scale:15,
				mark:[
					{
						longitude:114.420857,
						latitude:30.50733,
						iconPath:"../../../static/marker.png"
					}
				]
			}
		},
		methods: {
			phone(){
				uni.makePhoneCall({
					phoneNumber:"15629085742"
				})
			}
		}
	}
</script>

<style lang="scss">
.content{
	.imageStyle{
		width: 100%;
		height: 320rpx;
	}
	.info{
		padding: 10rpx 30rpx;
		font-size: 30rpx;
		view{
			line-height: 70rpx;
			border-bottom: 1px solid #f2f2f2;
		}
	}
	.map{
		width: 100%;
		height: 750rpx;
		
	}
}
</style>
