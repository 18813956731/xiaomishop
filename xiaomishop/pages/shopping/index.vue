<template>
	<view class="content">
<<<<<<< HEAD
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
			<text class="title">{{name}}</text>
		</view>
=======
		<goodslist ></goodslist>
		<view class="goods-carts">
			<goodsnav  />
		</view>
		<recommend></recommend>
>>>>>>> 田野
	</view>
</template>

<script>
<<<<<<< HEAD
=======
	import goodslist from "@/components/shopping/goodslist.vue"
	import goodsnav from "@/components/shopping/goodsnav.vue"
	import recommend from "@/components/shopping/recommend.vue"
	
>>>>>>> 田野
	export default {
		data() {
			return {
				title: 'Hello',
				name:"我的购物车"
			}
		},
<<<<<<< HEAD
=======
		components:{
			goodslist,
			goodsnav,
			recommend
		},
>>>>>>> 田野
		onLoad() {
		
		
		},
		methods: {

		}
	}
</script>

<style scoped>
.goods-carts {
		width: 100%;
		position: fixed;
		bottom: 117rpx;
	}

	
</style>
