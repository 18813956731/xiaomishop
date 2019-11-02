<template>
	<view class="mine-setup">
		<view class="hreder">账号管理</view>
		<view class="btn bt" @click="personal">
			<text>个人资料</text>
			<span class="iconfont icon-you"></span>
		</view>
		<view class="btn bt" @click="receiving">
			<text>收货地址</text>
			<span class="iconfont icon-you"></span>
		</view>
		<view class="hreder">关于</view>
		<view class="btn bt" @click="shopping">
			<text>关于商城</text>
			<span class="iconfont icon-you"></span>
		</view>
		<view class="btn bt" @click="feedback">
			<text>意见反馈</text>
			<span class="iconfont icon-you"></span>
		</view>
		<view class="btn bt" @click="rule">
			<text>协议规则</text>
			<span class="iconfont icon-you"></span>
		</view>
		<view class="btn bt" @click="Certificates">
			<text>资质证件</text>
			<span class="iconfont icon-you"></span>
		</view>
		<view class="btn bt" @click="user">
			<text>用户协议</text>
			<span class="iconfont icon-you"></span>
		</view>
		<view class="btn bt" @click="rivacy">
			<text>隐私a政策w</text>
			<span class="iconfont icon-you"></span>
		</view>
		<view class="footer">
			<view class="text" @click="sign">退出登录</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			//个人资料
			personal() {
				// this.$api.msg(`个人资料`);
				console.log("个人资料")
			},
			//收货地址
			Receiving() {
				console.log("收货地址")
			},
			//关于商城
			shopping() {
				console.log("123")
			},
			//意见反馈
			feedback() {
				console.log("123")
			},
			//协议规则
			rule() {
				console.log("123")
			},
			//资质证件
			Certificates() {
				console.log("123")
			},
			//用户协议
			user() {
				console.log("123")
			},
			//隐私政策
			user() {
				console.log("123")
			},
			sign(){
				console.log("3456")
			}
				
		}
	}
</script>

<style lang="scss">
	.hreder {
		font-size: 34rpx;
		text-indent: 25rpx;
		color: #555555;
		height: 100rpx;
		line-height: 100rpx;
		background-color: #F1F1F1;
	}

	.btn {
		height: 100rpx;
		line-height: 100rpx;
		font-size: 36rpx;
		text-indent: 30rpx;
		border-bottom: solid 2rpx #F1F1F1;

		.icon-you {
			float: right;
			margin-right: 40rpx;
			font-size: 16rpx;
			color: #C0C0C0;
		}
	}

	.footer {
		background-color: #F1F1F1;
		height: 200rpx;
		padding-top: 25rpx;

		.text {
			font-size: 37rpx;
			width: 88%;
			margin: auto;
			height: 100rpx;
			line-height: 100rpx;
			background-color: white;
			text-align: center;
		}
	}
</style>
