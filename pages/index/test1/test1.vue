<template>
	<view>
		<h1>{{num}}</h1>
		<button @click="num++" type="primary">数字+1</button>
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
			
		},
		onPullDownRefresh: () => {
			console.log("用户下拉刷新");
			//this.num=0;
		}
	}
</script>

<style>

</style>
