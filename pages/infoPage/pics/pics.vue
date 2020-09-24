<template>
	<view class="content">
		<scroll-view class="left" scroll-y>
			<view :class="currentIndex  === index?'active':''" @click="toggle(index)" v-for="index in 20">家居生活</view>
		</scroll-view>
		<scroll-view scroll-y class="right">
			<view class="item" v-for="(item,index) in imgArr">
				<image :src="item.src" @click="imgpreview(item.src)"></image>
				<text>{{item.text}}</text>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				currentIndex:1,
				imgArr:[{
					src:"../../../static/shequ/tu1.jpg",
					id:"001",
					text:"荣耀Play4T 全网通6GB+128GB大内存 极光蓝 4000mAh大电池 4800万AI摄影 6.39英寸魅眼屏"
				},{
					src:"../../../static/shequ/tu2.jpg",
					id:"002",
					text:"荣耀Play4T 全网通6GB+128GB大内存 极光蓝 4000mAh大电池 4800万AI摄影 6.39英寸魅眼屏"
				},{
					src:"../../../static/shequ/tu3.jpg",
					id:"003",
					text:"荣耀Play4T 全网通6GB+128GB大内存 极光蓝 4000mAh大电池 4800万AI摄影 6.39英寸魅眼屏"
				},{
					src:"../../../static/shequ/tu4.jpg",
					id:"004",
					text:"荣耀Play4T 全网通6GB+128GB大内存 极光蓝 4000mAh大电池 4800万AI摄影 6.39英寸魅眼屏"
				}]
			}
		},
		methods: {
			toggle(index){
				this.currentIndex = index
			},
			imgpreview(current){
				const urls = this.imgArr.map(item=>{
					return item.src
				})
				uni.previewImage({
					urls,
					current
				})
			}
		}
	}
</script>

<style lang="scss">
	page {
		height: 100%;
	}

	.content {
		height: 100%;
		display: flex;
		.left {
			width: 200rpx;
			height: 100%;
			border-bottom: 1px solid #eee;
			view {
				height: 100rpx;
				line-height: 100rpx;
				font-size: 30rpx;
				color: #333333;
				text-align: center;
				border-top: 1px solid #eee;
			}
			.active{
				background: #C51D02;
				color: #fff;
			}
		}
		.right{
			height: 100%;
			width: 520rpx;
			margin: 10rpx auto;
			.item{
				image{
					width: 520rpx;
					height: 520rpx;
					border-radius: 10rpx;
				}
				text{
					font-size: 30rpx;
					line-height: 50rpx;
				}
			}
		}
	}
</style>
