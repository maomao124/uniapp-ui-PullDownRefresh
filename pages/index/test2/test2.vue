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
			}
		},
		onPullDownRefresh: () => {
			console.log("用户下拉刷新");
			//this.num=0;
		}
	}
</script>

<style>
button{
	margin: 5px;
}
</style>
