<template>
	<view class="content">
		<swiper class="swiper" indicator-dots autoplay :interval="1000" circular>
			<swiper-item v-for="(item,index) in imgList">
				<image :src="item.src" @load="imgLoad"></image>
			</swiper-item>
		</swiper>
		<view class="iconList">
			<view class="icon-item" v-for="(item,index) in iconList" @click="navItem(item)">
				<view class="img-icon">
					<image :src="item.src"></image>
				</view>
				<view class="text-item">
					{{item.text}}
				</view>
			</view>
		</view>
		<view class="commend" ref="tabControl" :class="{flexd:isTabFixed}">
			推荐商品
		</view>
		<!-- 商品列表 -->
		<commodity-info></commodity-info>
	</view>
</template>
<!-- 92.168.100.57:6001 -->
<script>
	import commodityInfo from '../../components/commodityInfo.vue'
	export default {
		components:{
			"commodity-info":commodityInfo
		},
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
				}],
				iconList: [{
					src: "../../static/homeIcon/shop.png",
					text: "黑马超市",
					path:"/pages/infoPage/goods/goods"
				}, {
					src: "../../static/homeIcon/message.png",
					text: "联系我们",
					path:"/pages/infoPage/contact/contact"
				}, {
					src: "../../static/homeIcon/tupian.png",
					text: "社区图片",
					path:"/pages/infoPage/pics/pics"
				}, {
					src: "../../static/homeIcon/shipin.png",
					text: "学习视频",
					path:"/pages/infoPage/videos/videos"
				}],
				
				tabOffsetTop: 0,
				isLoad: false,
				isTabFixed: false
			}
		},
		onLoad() {

		},
		methods: {
			navItem(item){
				console.log(item.path)
				uni.navigateTo({
					url:item.path
				})
			},
			imgLoad() {
				if (!this.isLoad) {
					this.tabOffsetTop = this.$refs.tabControl.$el.offsetTop
					this.isLoad = true
				}
			},
			//節流
			throttle(fn,delay = 300){
				let timer = null;
				return function(){
					if(timer){
						return
					}
					timer = setTimeout(()=>{
						fn.apply(this,arguments)
						timer = null
					},delay)
				}
			},
			//获取滚动距离
			handleScroll () {
			  var scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop
			  if(scrollTop>this.tabOffsetTop - 44){
				  this.isTabFixed = true
			  }else{
				  this.isTabFixed = false
			  }
			}
		},
		mounted() {
			console.log(window)
			let that = this;
			window.addEventListener('scroll', this.throttle(this.handleScroll,50))
		},
		deactivated() {
			window.removeEventListener('scroll', this.throttle(this.handleScroll,50))
		}
	}
</script>

<style lang="scss">
	.content {
		background-color: #f2f2f2;
		swiper {
			width: 750rpx;
			height: 380rpx;

			image {
				width: 100%;
				height: 100%;
			}
		}
		.iconList {
			width: 100%;
			height: 200rpx;
			display: flex;
			background-color: #fff;
			padding-bottom: 30rpx;
			.icon-item {
				flex: 1;
				.img-icon {
					width: 120rpx;
					height: 120rpx;
					background: #C51D02;
					border-radius: 50%;
					display: flex;
					justify-content: center;
					align-items: center;
					margin: 20rpx auto;

					image {
						width: 70rpx;
						height: 70rpx;
						text-align: center;
					}
				}
				.text-item {
					font-size: 30rpx;
					text-align: center;
				}
			}
		}
		.commend {
			width: 100%;
			height: 80rpx;
			line-height: 80rpx;
			text-align: center;
			background: #fff;
			margin-top: 10rpx;
			font-size: 34rpx;
			color: #C51D02;
			letter-spacing: 10rpx;
			&.flexd {
				position: fixed;
				left: 0;
				right: 0;
				top: 88rpx;
				z-index:10;
				margin-top: 0;
				border-bottom: 10rpx solid #f2f2f2;
			}
		}
	}
</style>
