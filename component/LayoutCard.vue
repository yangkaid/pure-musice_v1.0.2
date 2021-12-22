<template>
	<view class="layout">
		<view class="title">
			<view class="title-left">
				<text>{{title}}</text>
			</view>
			<view class="title-right" @click="jumpToMore">
				<text>更多</text>
				<u-icon name="arrow-right" size="15"></u-icon>
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
			title: String,
			jumpPage: String
		},
		methods: {
			jumpToMore() {
				uni.$u.route({
					url: `${this.jumpPage}`
				})
			}
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

			.title-right {
				display: flex;
				align-items: center;
				border: 1rpx solid #C4C6C9;
				border-radius: 20rpx;
				padding: 5rpx;
				font-size: 23rpx;
			}
		}
	}
</style>
