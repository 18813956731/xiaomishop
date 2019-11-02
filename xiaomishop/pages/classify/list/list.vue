<template>
	<view id="content">
		<view class="head">
			<!-- 头部导航 -->
			<view class="itemst" v-for="item in head">
				<view class="items-icon">{{item}}</view>
				<view class="icon">
					<view class="icotop">
						<icon type="black" class="iconfont icon-paixu-shengxu"></icon> 
					</view>
					<view class="icobot">
						<icon type="black" class="iconfont icon-paixu-jiangxu"></icon>
					</view>
				</view>
			</view>
			<view class="items">筛选</view>
		</view>
		<view class="conter">
			<!-- 商品 -->
			<view v-for="item in 10">
			<view class="dl" v-for="(item,index) in datas">
				<view class="dt">
					<image src="../../../static/images/demo/list/1.jpg"></image>
				</view>
				<view class="dd">
					<view class="name">{{item.name}}</view>
					<span class="span">{{item.txt}}</span>
					<view class="rmb">$<span style="font-size: 45rpx;">{{item.rmb}}</span></view>
					<view class="pinglun">{{item.pinglun}}</view>
				</view>
			</view>
			</view>
		</view>
	</view>
</template>

<script>
	
	export default {
		data() {
			return {
				head:["综合","销量","价格"],
				datas:[{
					name:"真无线蓝牙耳机",
					txt:"雅致简约/分体式入耳/收纳盒充电/蓝牙5.0、触控操作",
					rmb:"199",
					pinglun:"1348"
				}]
			}
		},
		methods: {
			
		},
		onNavigationBarButtonTap(e){
		console.log(e)
		console.log(111)
		}
	}
</script>

<style scoped>
.head{
	height: 100rpx;
	border: #999999 1px solid;
	overflow: hidden;
}
.itemst{
	text-align: center;
	border: #999999 1px solid;
	width: 180rpx;
	float: left;
}
.icon{
	width: 30rpx;
	height: 100rpx;
	float: left;
}
.items-icon{
	float: left;
}
.icotop{
	position: relative;
}
.iconfont{
	width: 30rpx;
	height: 49rpx;
	float: left;
}
/* 商品 */
.dl{
	padding: 30rpx;
	border-bottom: #999999 1px solid;
	overflow: hidden;
}
.dl .dt{
	float: left;
	width: 250rpx;
	height: 250rpx;
}

.dl .dd{
	margin-left: 20rpx;
	width: 400rpx;
	float: left;
}
.dt image{
	width: 100%;
	height: 100%;
}
.dl .dd .span,.pinglun{
	color: #999999;
	font-size: 30rpx;
}
.dl .dd .name{
	padding-top: 10rpx;
	font-weight: 600;
}
/* 价格 */
.rmb{
	color: orange;
}
</style>
