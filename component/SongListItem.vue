<template>
	<view class="list-item">
		<image src="../static/list-cover.jpg" class="image-item"></image>
		<view class="description">
			{{description}}
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			description: {
				type: String,
				default: ''
			},
		},
	}
</script>

<style lang="scss" scoped>
	.list-item {
		display: inline-flex;
		flex-direction: column;
		margin-left: 16rpx;
		margin-bottom: 33rpx;
		width: 220rpx;
		.image-item {
			width: 217rpx;
			height: 208rpx;
			border-radius: 10rpx;
			margin-bottom: 20rpx;
		}
		.description {
			white-space: normal;
			font-size: 20rpx;
			font-weight: 500;
		}
		
	}
</style>
