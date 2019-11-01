<template>
	<view class="content">
		<heads></heads>
		<goodslist></goodslist>
	</view>
</template>

<script>
	import heads from "../../components/shopping/heads.vue"
	import goodslist from "../../components/shopping/goodslist.vue"
	export default {
		data() {
			return {
				name:"我的购物车"
			}
		},
		components:{
			heads,
			goodslist
		},
		onLoad() {

		},
		methods: {
			
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
