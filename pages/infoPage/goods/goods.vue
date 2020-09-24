<template>
	<view class="content">
		<commodity-info></commodity-info>
	</view>
</template>

<script>
	import commodityInfo from '../../../components/commodityInfo.vue'
	export default {
		components:{
			"commodity-info":commodityInfo
		},
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	.content{
		background: #f2f2f2;
	}
</style>
