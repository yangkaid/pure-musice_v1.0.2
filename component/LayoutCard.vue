<template>
	<view class="layout">
		<view class="title">
			<view class="title-left">
				<text>{{title}}</text>
			</view>
			<view class="title-right">
				<text>更多</text>
			</view>
		</view>
		<view class="content">
			<slot></slot>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			title: {
				type: String,
				default: '推荐'
			},
		},
		
	}
</script>

<style lang="scss" scoped>
	.layout {
		display: flex;
		flex-direction: column;
		margin-top: 20rpx;
		.title {
			display: flex;
			justify-content: space-between;
			align-items: center;
			height: 80rpx;
			margin: 10rpx 20rpx;
		}
	}
</style>
