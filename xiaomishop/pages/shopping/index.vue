<template>
	<view class="content">
		<goodslist ></goodslist>
		<view class="goods-carts">
			<goodsnav/>
		</view>
		<recommend></recommend>
	</view>
</template>

<script>
	import goodslist from "@/components/shopping/goodslist.vue"
	import goodsnav from "@/components/shopping/goodsnav.vue"
	import recommend from "@/components/shopping/recommend.vue"
	export default {
		data() {
			return {
				title: 'Hello',
				name:"我1的购物车"
			}
		},

		components:{
			goodslist,
			goodsnav,
			recommend
		},
		onLoad() {
		
		},
		methods: {}
}
</script>

<style scoped="scoped">

	
</style>
