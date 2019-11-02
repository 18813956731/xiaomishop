<template>
	<view id="content">
		<view class="scroll-Left">
			<scroll-view scroll-y="false" class="scroll-y" :style="{height:phoneHeight+'px'}">
				<view v-for="(item,index) in 20" class="classification" @click="tab(index)">分类{{index+1}}</view>
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
		<!-- <image src="../../static/images/demo/list/1.jpg"></image> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				classif:0,
				title: 'Hello',
				"phoneHeight": 0,
				"phoneHeights": 0,
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
			// uni.request({
			// 	url: 'http://ceshi3.dishait.cn/api/index_category/data',
			// 	success(res) {
			// 		console.log(res);
			// 	}
			// })
		},
		methods: {
			tab:function(e) {
				this.classif=e
				console.log(e)
			},
			Jump(e){
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
	.classification {
		padding: 25rpx;
		border-bottom: solid 1rpx;
		border-right: solid 1rpx;
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
