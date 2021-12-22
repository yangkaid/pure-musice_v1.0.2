<template>
	<view class="song-list">
		<uni-list :border="false">
			<!-- <uni-list-item title="列表文字" note="什么是列表描述信息" v-for="i in 3" :key="i"></uni-list-item> -->
			<uni-list-item title="歌曲列表" clickable v-for="i in 5" :key="i">
				<view slot="body" class="song-item">
					<view class="item-left">
						<view class="song-id">1</view>
						<view class="song-info">
							<view class="song-name">牧马城市</view>
							<view class="singer">毛不易 - 老男孩电视原声带</view>
						</view>
					</view>
					<view class="item-right"><uni-icons type="more" size="25"></uni-icons></view>
				</view>
			</uni-list-item>
		</uni-list>
	</view>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.song-list {
	/deep/ .uni-list-item__container {
		padding: 0;
	}
	.song-item {
		height: 110rpx;
		width: 100%;
		padding: 10rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
		.item-left {
			display: flex;
			align-items: center;
			.song-id {
				width: 55rpx;
				height: 55rpx;
				font-size: 30rpx;
				margin-right: 17rpx;
				display: flex;
				align-items: center;
				justify-content: center;
			}
			.song-info {
				display: flex;
				flex-direction: column;
				.song-name {
					font-size: 30rpx;
					font-weight: 500;
					letter-spacing: 5rpx;
					margin-bottom: 5rpx;
				}
				.singer {
					font-size: 20rpx;
					color: #c4c4c4;
				}
			}
		}
		.item-right {
			display: flex;
			align-items: center;
			justify-content: center;
			margin-right: 15rpx;
		}
	}
}
</style>
