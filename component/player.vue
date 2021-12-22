<template>
	<view class="player">
		<view class="left">
			<image src="../static/list-cover.jpg" class="cover"></image>
			<view class="song-info">
				<view class="title">这不是巧了嘛</view>
				<view class="singer">王力宏</view>
			</view>
		</view>
		<view class="right">
			<view @click="showControl = !showControl">
				<image src="../static/pause.svg" class="control" v-show="showControl"></image>
				<image src="../static/play.svg" class="control" v-show="!showControl"></image>
			</view>
			<image src="../static/music-list.svg" class="music-list"></image>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				showControl: false
			}
		},
	}
</script>

<style lang="scss" scoped>
.player {
	display: flex;
	align-items: center;
	justify-content: space-between;
	width: 94%;
	height: 98rpx;
	background-color: rgba(47, 107, 120, 0.85);
	border-radius: 25rpx;
	position: fixed;
	bottom: 0;
	padding: 8rpx 24rpx;
	.left {
		display: flex;
		align-items: center;
		.cover {
			width: 90rpx;
			height: 90rpx;
			border-radius: 10rpx;
			margin-right: 18rpx;
		}
		.title {
			font-weight: normal;
			font-size: 30rpx;
			line-height: 116%;
			color: #ffffff;
			margin-bottom: 10rpx;
		}
		.singer {
			font-weight: normal;
			line-height: 116%;
			font-size: 24rpx;
			color: #c4c4c4;
		}
	}
	.right {
		display: flex;
		align-items: center;
		.control {
			width: 64rpx;
			height: 64rpx;
			margin-right: 10rpx;
		}
		.music-list {
			width: 48rpx;
			height: 48rpx;
		}
	}
}
</style>
