<template>
	<view>
		<h1>{{num}}</h1>
		<button @click="num++" type="primary">数字+1</button>
		<button @click="refresh()" type="primary">手动刷新</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				num:0,
			}
		},
		methods: {
			refresh()
			{
				console.log("手动刷新");
				uni.startPullDownRefresh({
					success: () => {
						console.log("手动刷新成功");
					},
					fail: () => {
						console.log("手动刷新失败");
					}
				})
			},
			reset()
			{
				this.num=0;
			}
		},
		onPullDownRefresh: () => {
			console.log("用户下拉刷新");
			this.reset();
			setTimeout(function()
			{
				console.log("停止刷新");
				uni.stopPullDownRefresh();
			},500)
			
		}
	}
</script>

<style>
button{
	margin: 5px;
}
</style>
