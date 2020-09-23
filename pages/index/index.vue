<template>
	<view class="content">
		<swiper class="swiper" indicator-dots autoplay :interval="1000" circular>
			<swiper-item v-for="(item,index) in imgList" class="img-item">
				<image :src="item.src" class="imgStyle"></image>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgList: [{
					src: "../../static/swipper/img1.jpg",
					text: "图片1",
					id: '001'
				}, {
					src: "../../static/swipper/img2.jpg",
					text: "图片2",
					id: '002'
				}, {
					src: "../../static/swipper/img3.jpg",
					text: "图片3",
					id: '003'
				}]
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.content {
		swiper {
			width: 750rpx;
			height: 380rpx;
			image{
				width:100%;
				height: 100%;
			}
		}
	}
	
</style>
