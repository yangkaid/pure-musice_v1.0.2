<template>
	<LayoutCard title="推荐音乐" jumpPage="pages/song-list/index">
		<swiper :indicator-dots="false" :autoplay="false" :style="{ height: ' 400rpx' }" next-margin="60rpx">
			<swiper-item v-for="(item, index) in songList" :key="index">
				<view class="swiper-item" v-for="(songGroup, index1) in item" :key="index1">
					<SongSwiper :songName="songGroup.songName" :singer="songGroup.singer"></SongSwiper>
				</view>
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
		props: {
			songList: {
				type: Array,
				default: []
			},
		},
		data() {
			return {};
		}
	};
</script>

<style lang="scss" scoped>

</style>
