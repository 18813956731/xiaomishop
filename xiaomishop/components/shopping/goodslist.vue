<template>
	<view id="content">
		<view class='car-list'>
						<!-- 购物车产品 -->
						<view class='car-item'>
							<!--列表项-->
							<view class='car-prod'>
								<!-- 商品信息-->
								<view class='goods-info'>
									<view class='goods-info-inner'>
										<view class='checkbox'></view>
										<view class='goods-image'>
											<image src="../../static/images/demo/list/1.jpg"></image>
										</view>
										<view class='good-info'>
											<view class='name'>华为matax210</view>
											<view class='lx'>火焰红 64G 标配</view>
											<view class='price'>￥3541</view>
											<amount :value="numberValue" class="numbers" @change="change"></amount>
										</view>
									</view>
								</view>
							</view>
						</view>
						<!-- 没有商品信息 -->
						<view v-if='1==0'>
								购物车空空如也，赶紧去挑选你心意的产品吧~~~~~
						</view>
					</view>
	</view>
</template>

<script>
	import amount from "../../components/shopping/amount.vue"
	export default{
		data(){
			return{
				numberValue:1
			}
		},
		components:{
			amount
		},
		methods:{
			change(value) {
				this.numberValue = value
				console.log("商品数量"+value)
			}
		}
	}
</script>

<style scoped>
	.car-list {
			padding-bottom: 47px;
		}
		
		.car-item {
			position: relative;
			overflow: hidden;
		}
		
		.car-item .car-prod {
			border-top: 1px solid #ddd;
			position: relative;
			left: 0;
			box-sizing: border-box;
			overflow: hidden;
		}
		
		.car-prod .btn-delete {
			float: left;
			border-radius: 0;
			font-size: 30rpx;
			box-sizing: border-box;
			width: 50px;
			background-color: #e64340;
			color: #fff;
			text-align: center;
			height: 260rpx;
			line-height: 260rpx;
		}
		
		.goods-info {
			float: left;
			box-sizing: border-box;
			position: relative;
			background: url(https://cdn.it120.cc/images/weappshop/gou.png) no-repeat 30rpx center;
			background-size: 40rpx auto;
		}
		
		.goods-info.active {
			background-image: url(https://cdn.it120.cc/images/weappshop/gou-red.png);
		}
		
		.goods-info .goods-info-inner {
			display: flex;
			padding: 40rpx 0;
		}
		
		.goods-info-inner .checkbox {
			width: 120rpx;
		}
	
		.goods-info-inner .goods-image{
			width: 180rpx;
			height: 180rpx;
			border: 1px solid #CCC;
			display: flex;
		}
		.goods-image>image{
			width: 150rpx;
			height: 150rpx;
			display: block;
			margin: auto;
		}
		.goods-info-inner .good-info {
			flex: 1;
			padding: 0 20rpx;
		}
		
		.goods-info-inner .good-info .name {
			line-height: 70rpx;
			white-space: nowrap;
			overflow: hidden;
			text-overflow: ellipsis;
			box-sizing: border-box;
		}
		.lx{
			line-height: 60rpx;
			padding: 10rpx 0;
			white-space: nowrap;
			font-size: 30rpx;
			overflow: hidden;
			text-overflow: ellipsis;
			box-sizing: border-box;
			background-color: #F1F1F1;
		}
		.price {
			float: left;
			color: #FD7112;
		}
		
		.numbers {
			float: right;
		}
		
		.goods-info-inner .good-info {
			height: 90rpx;
			line-height: 90rpx;
		}
</style>
