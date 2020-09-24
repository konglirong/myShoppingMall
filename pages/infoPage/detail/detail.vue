<template>
	<view>
		详情页
		{{id}}
	</view>
</template>

<script>
	export default {
		data() {
			return {
				id:'',
			}
		},
		onLoad(option) {
			console.log(option)
			this.id = option.id
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
