<template>
	<view id="content">
		<view class="scroll-Left">
			<scroll-view scroll-y="false" class="scroll-y" :style="{height:phoneHeight+'px'}">
				<view v-for="(item,index) in 10">
					<view class="fenlei" :class="tabcss==index?'tabcolor':''" :key="index" @click="tabs(index)">分类{{index+1}}</view>
				</view>
			</scroll-view>
		</view>
		<view class="commodity-Right">
			<scroll-view scroll-y="false" class="scroll-yr" :style="{height:phoneHeights+'px'}">
				<ul class="commodity-ul" v-for="(item,indexs) in 6">
					<li class="li-item" v-for="(val,index) in list_img" @click="Jump(item)">
						<image :src="val"></image>
						<view class="Trade-Name">分类{{classif}}商品{{index+1+(indexs*6)}}</view>
					</li>
				</ul>
			</scroll-view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tabcss:0,
				classif:0,
				"phoneHeight": 0,
				"phoneHeights": 0,
				"classification":'',
				"list_img": [
					"../../static/images/demo/list/1.jpg",
					"../../static/images/demo/list/2.jpg",
					"../../static/images/demo/list/3.jpg",
					"../../static/images/demo/list/4.jpg",
					"../../static/images/demo/list/5.jpg",
					"../../static/images/demo/list/6.jpg"
				]
			}
		},
		onLoad() {
			let _this = this
			uni.getSystemInfo({
				success(res) {
					// 获取窗口高度
					_this.phoneHeight = res.windowHeight;
					_this.phoneHeights = res.windowHeight;
					// console.log(res.windowHeight)
				}
			});
			uni.request({
				url: 'http://ceshi3.dishait.cn/api/index_category/data',
				success(res) {
					// 分类
					_this.classification=res.data.data.category
					console.log(res.data.data);
				}
			})
		},
		methods: {
			// 切换样式
			tabs:function(e){
				let _this=this
				_this.tabcss=e;
				_this.classif=e;
			},
			// 跳转列表页
			Jump:function(e){
				uni.navigateTo({
					url:"list/list"
				})
			}
		}
	}
</script>

<style scoped>
	* {
		padding: 0;
		margin: 0;
	}

	li {
		list-style: none;
	}

	#content {
		height: 100%;
		width: 100%;
	}

	/* 左边栏 */
	.scroll-Left {
		float: left;
		height: auto;
	}

	.scroll-y {
		width: 180rpx;
	}

	/* tab切换 */
	.fenlei{
		font-size: 30rpx;
		padding: 25rpx 0rpx;
		text-align: center;
		border-bottom: solid 1rpx #DDDDDD;
		border-right: solid 1rpx #DDDDDD;
		width: 180rpx;
		border-left: #FFFFFF 7rpx solid;
	}
	.tabcolor{
		color: #FD964F;
		border-left: #FD964F 7rpx solid;
	}

	/* 右边商品 */
	.commodity-Right {
		float: left;
		width: 570rpx;
	}

	.li-item {
		text-align: center;
		float: left;
		width: 188rpx;
		height: 188rpx;
		/* border: #007AFF 1px solid; */
	}

	.li-item image {
		width: 70%;
		height: 70%;
	}

	.Trade-Name {
		font-size: 25rpx;
	}
</style>
