<template>
	<view class="commodityList" ref="viewBox">
		<view class="commodity-item" v-for="item in shopList">
			<image src="../static/phone1.jpg"></image>
			<view class="price">
				2195
				<text>2999</text>
			</view>
			<text class="desc">
				华为 HUAWEI P40 麒麟990 5G SoC芯片 5000万超感知徕卡三摄 30倍数字变焦 8GB+128GB冰霜银全网通5G手机
			</text>
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				shopList: [4, 5, 6, 56, 4, 56, 45, 56, 5, 8],
			};
		}
	}
</script>

<style lang="scss">
	// 商品列表
	.commodityList {
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		margin: 10rpx 12rpx;

		.commodity-item {
			width: 49%;
			height: 480rpx;
			background: #fff;
			padding-top: 30rpx;
			margin-bottom: 10rpx;

			image {
				width: 320rpx;
				height: 320rpx;
				display: block;
				margin: 0 auto;
			}

			.price {
				font-size: 30rpx;
				font-weight: bold;
				color: #C51D02;
				text-align: left;
				margin-left: 20rpx;

				>text {
					color: #999999;
					font-size: 26rpx;
					text-decoration: line-through;
					margin-left: 40rpx;
					font-weight: normal;
				}
			}

			.desc {
				font-size: 28rpx;
				color: #333333;
				padding: 0 20rpx;
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
		}
	}
</style>
