<template>
	<view class="content">
		<view class="item" v-for="(item,index) in imgArr" @click="itemClick(item)">
			<view class="left">
				<image :src="item.src"></image>
			</view>
			<view class="right">
				<view class="word">
					{{item.text}}
				</view>
				<view class="info">
					<text>发表时间：2020-9-23</text>
					<text class="cishu">浏览：120次</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgArr:[{
					src:"../../static/shequ/tu1.jpg",
					id:"001",
					text:"荣耀Play4T 全网通6GB+128GB大内存 极光蓝 4000mAh大电池 4800万AI摄影 6.39英寸魅眼屏"
				},{
					src:"../../static/shequ/tu2.jpg",
					id:"002",
					text:"荣耀Play4T 全网通6GB+128GB大内存 极光蓝 4000mAh大电池 4800万AI摄影 6.39英寸魅眼屏"
				},{
					src:"../../static/shequ/tu3.jpg",
					id:"003",
					text:"荣耀Play4T 全网通6GB+128GB大内存 极光蓝 4000mAh大电池 4800万AI摄影 6.39英寸魅眼屏"
				},{
					src:"../../static/shequ/tu4.jpg",
					id:"004",
					text:"荣耀Play4T 全网通6GB+128GB大内存 极光蓝 4000mAh大电池 4800万AI摄影 6.39英寸魅眼屏"
				}]
			}
		},
		methods: {
			itemClick(item){
				let id = item.id
				uni.navigateTo({
					url:"/pages/infoPage/detail/detail?id="+id
				})
			}
		}
	}
</script>

<style lang="scss">
	.content{
		background: #fff;
		width: 100%;
		.item{
			display: flex;
			padding: 10rpx 20rpx;
			border-bottom: 1px solid #C51D02;
			.left{
				width: 30%;
				image{
					min-width: 200rpx;
					max-width: 200rpx;
					height: 150rpx;
				}
			}
			.right{
				width: 70%;
				margin-top: 8rpx;
				.word{
					font-size: 30rpx;
					overflow: hidden;
					text-overflow: ellipsis;
					/* 超出部分省略号 */
					display: -webkit-box;
					/** 对象作为伸缩盒子模型显示 **/
					-webkit-box-orient: vertical;
					/** 设置或检索伸缩盒对象的子元素的排列方式 **/
					-webkit-line-clamp: 2;
					/** 显示的行数 **/
				}
				.info{
					font-size: 26rpx;
					margin-top: 20rpx;
					.cishu{
						margin-left: 40rpx;
					}
				}
			}
		}
	}

</style>
