<template>
	<view class="music-list">
		<view class="header">
			<view class="back">
				<i class="fa fa-angel-left"></i>
			</view>
			<view class="text">
				<h4 class="title">歌手</h4>
			</view>
		</view>
		<view class="list">
			<view class="music-list-wrapper" style="transition-property: transform; 
			transition-timing-function: cubic-bezier(0.23, 1, 0.32, 1); 
			transition-duration: 0ms; transform: translate(0px, -18px) translateZ(0px);"></view>
			<view class="bg-img" :style="{backgroundImage: 'url('+pic+')'}">
				<view class="filter"></view>
				<view class="text">
					<h4 class="list-title">{{texts}}</h4>
					<p class="update"></p>
				</view>
			</view>
			<view class="song-list-wrapper">
				<view class="sequence-play">
					<i class="iconfont icon-bofangicon"></i>
					<span class="text">播放全部</span>
					<span class="count">(共{{ids.length}}首)</span>
				</view>
				<view class="song-list">
					<ul>
						<li v-for="(item,index) in songs" class="item" @click="goPlay">
							<p class="count">{{index+1}}</p>
							<div class="content">
								<view class="name">{{item.name}}</view>
								<p class="desc">{{item.ar[0].name}}</p>
							</div>
						</li>
					</ul>
				</view>
			</view>
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				ids: [],
				sendids: "",
				pic: '',
				songs: [],
				texts: "",
				count: ""
			}
		},
		onLoad(option) {
			//console.log(option)			
			uni.request({
				url: "http://127.0.0.1:3000/playlist/detail",
				data: {
					id: option.id
				},
				success: (res) => {
					//console.log(res.data)
					let getId = res.data.playlist.trackIds
					this.pic = res.data.playlist.coverImgUrl;
					this.texts = res.data.playlist.name;
					for (let i = 0; i < getId.length; i++) {
						this.ids.push(getId[i].id)
					}
					//console.log(this.ids)
					this.sendids = this.ids.join()
					//console.log(this.sendids)
					uni.request({
						url: "http://127.0.0.1:3000/song/detail",
						data: {
							ids: this.sendids
						},
						success: (res) => {
							console.log(res.data)
							this.songs = res.data.songs
						}
					})
				}
			})
		},
		methods: {
			goPlay() {
				uni.navigateTo({
					url:"../play/index"
				})
			}
		},
	}
</script>
<style scoped="scoped">
	* {
		margin: 0px;
		padding: 0px;
	}

	li {
		list-style: none;
	}

	.music-list {
		position: fixed;
		z-index: 1000;
		top: 0;
		left: 0;
		bottom: 0;
		right: 0;
		background: #f2f3f4;
	}

	.header {
		position: fixed;
		top: 0;
		width: 100%;
		height: 44px;
		color: #fff;
		z-index: 100;
	}

	.back {
		position: absolute;
		top: 0;
		left: 4px;
	}

	.fa-angel-left {
		padding: 5px 10px;
		font-size: 30px;
	}

	.fa {
		display: inline-block;
		font: normal normal normal 14px/1 FontAwesome;
		text-rendering: auto;
		-webkit-font-smoothing: antialiased;
		font-size: inherit;
	}

	.fa-angle-left:before {
		content: "\F104";
	}

	.header .text {
		position: absolute;
		left: 38px;
		line-height: 44px;
		font-size: 16px;
		text-overflow: ellipsis;
		overflow: hidden;
		white-space: nowrap;
	}

	.title {}

	.list {
		position: fixed;
		top: 0;
		bottom: 0;
		width: 100%;
		background: #f2f3f4;
	}

	.bg-img {
		position: relative;
		width: 100%;
		height: 0;
		padding-top: 75%;
		transform-origin: top;
		background-size: cover;
		background-position: 0 30%;
		pointer-events: auto;
	}

	.filter {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: #000;
		opacity: .2;
	}

	.bg-img .text {
		position: absolute;
		width: 80%;
		height: 40px;
		bottom: 50px;
		left: 20px;
		color: #fff;
		z-index: 100;
	}

	.list-title {
		position: absolute;
		bottom: 0;
		font-style: italic;
		font-size: 18px;
		line-height: 18px;
		font-weight: 700;
		letter-spacing: 1px;
	}

	.update {
		position: absolute;
		top: 45px;
		left: 7px;
		line-height: 14px;
		font-size: 11px;
	}

	.fa-headphones:before {
		content: "\F025";
	}

	.song-list-wrapper {
		padding: 7px 0 20px;
		border-radius: 10px;
		position: relative;
		top: -20px;
		background: #f2f3f4;
	}

	.sequence-play .iconfont {
		font-size: 18px;
		color: #2e3030;
		padding-right: 14px;
	}

	.icon-bofangicon:before {
		content: "\E603";
	}

	.sequence-play .text {
		font-size: 16px;
	}

	.sequence-play .count {
		font-size: 14px;
		color: #757575;
	}

	.song-list .item {
		position: relative;
		display: flex;
		align-items: center;
		box-sizing: border-box;
		height: 60px;
		border-bottom: 1px solid #e4e4e4;
	}

	.song-list .item .count {
		flex: 0 0 50px;
		width: 50px;
		text-align: center;
		color: #757575;
	}

	.song-list .item .content {
		flex: 1;
		line-height: 20px;
		overflow: hidden;
	}

	.name {
		margin-top: 4px;
		width: 80%;
		text-overflow: ellipsis;
		overflow: hidden;
		white-space: nowrap;
		color: #2e3030;
	}

	.desc {
		text-overflow: ellipsis;
		overflow: hidden;
		white-space: nowrap;
		width: 80%;
		font-size: 12px;
		color: #757575;
	}
</style>
