<template>
	<view class="rank-item">
		<view class="item-left">
			<view class="rank-name">新歌榜</view>
			<image src="../static/list-cover.jpg" class="rank-cover"></image>
		</view>
		<view class="item-right">
			<view class="song" v-for="i in 3" :key="i">
				<view>
					<text class="name">1、无名的人</text>
					<text class="singer">- 毛不易</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script></script>

<style lang="scss" scoped>
.rank-item {
	display: flex;
	width: 687rpx;
	height: 270rpx;
	align-items: center;
	justify-content: center;
	background-color: #e2e9ef;
	border-radius: 20rpx;
	margin-top: 22rpx;
	.item-left {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin-right: 76rpx;
		.rank-name {
			font-size: 40rpx;
			color: #3d73be;
			margin-bottom: 22rpx;
		}
		.rank-cover {
			width: 140rpx;
			height: 130rpx;
			border-radius: 10rpx;
		}
	}
	.item-right {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		margin-top: 70rpx;
		.song {
			margin-bottom: 28rpx;
		}
	}
}
</style>
