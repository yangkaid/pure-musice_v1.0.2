<template>
	<view class="song-swiper-item">
		<image :src="cover" class="song-image"></image>
		<view class="song-info">
			<text class="name">{{songName}}</text>
			<text class="singer">{{singer}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			cover: String,
			songName: String,
			singer: String
		},
	}
</script>

<style lang="scss" scoped>
.song-swiper-item {
	display: flex;
	align-items: center;
	margin-top: 15rpx;
	height: 120rpx;
	.song-image {
		width: 111rpx;
		height: 109rpx;
		margin-right: 26rpx;
		border-radius: 10rpx;
	}
	.song-info {
		display: flex;
		flex-direction: column;
		.name {
			font-weight: 600;
			margin-bottom: 24rpx;
		}
		.singer {
			font-size: 30rpx;
			color: #909090;
		}
	}
}
</style>
