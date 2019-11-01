<template>
	<view id="content">
		<view class="head">
			<view class="tlt">
				<text>购物车</text>
			</view>
			<view class="redact">
				<text @click="redact">编辑</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			redact(){
				console.log("我是编辑")
			}
		}
	}
</script>

<style scoped>
	.head{
		display: flex;
		justify-content: center;
	}
	.redact{
		margin-left: 200rpx;
	}
</style>

