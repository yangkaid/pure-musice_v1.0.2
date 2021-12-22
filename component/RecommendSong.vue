<template>
	<LayoutCard title="推荐音乐" jumpPage="pages/song-list/index">
		<swiper :indicator-dots="false" :autoplay="false" :style="{ height: ' 400rpx' }" next-margin="60rpx">
			<swiper-item v-for="(item, index) in songList" :key="index">
				<view class="swiper-item" v-for="(songGroup, index1) in item" :key="index1">
					<SongSwiper :songName="songGroup.name" :singer="songGroup.singer" :cover="songGroup.album_cover" @click.native="playSong(songGroup)"></SongSwiper>
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
		songList: Array
	},
	data() {
		return {};
	},
	methods: {
		playSong(songInfo) {
			console.log(songInfo);
		}
	}
};
</script>

<style lang="scss" scoped></style>
