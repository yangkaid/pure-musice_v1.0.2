<template>
	<LayoutCard title="推荐音乐">
		<swiper :indicator-dots="false" :autoplay="false" :style="{ height: ' 400rpx' }" next-margin="60rpx">
			<swiper-item v-for="(item, index1) in songList" :key="index1">
				<view class="swiper-item" v-for="(songGroup, index2s) in item" :key="index2"><SongSwiper :songName="songGroup.songName" :singer="songGroup.singer"></SongSwiper></view>
			</swiper-item>
		</swiper>
	</LayoutCard>
</template>

<script>
import LayoutCard from './LayoutCard.vue';
import SongSwiper from './SongSwiper.vue';
export default {
	components: {
		LayoutCard,
		SongSwiper
	},
	data() {
		return {
			songList: [
				[
					{
						songName: '如果当时',
						singer: '许嵩 - 自定义'
					},
					{
						songName: '断桥残雪',
						singer: '许嵩 - 许嵩早期单曲集'
					},
					{
						songName: '想着你',
						singer: '毛不易 - 中国潮音'
					}
				],
				[
					{
						songName: '有关于你',
						singer: '金玟岐 - 有关于你'
					},
					{
						songName: '丁香花',
						singer: '唐磊 - 丁香花'
					},
					{
						songName: '丁香花',
						singer: '唐磊 - 丁香花'
					}
				]
			]
		};
	}
};
</script>

<style lang="scss" scoped>

</style>
