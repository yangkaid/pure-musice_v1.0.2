<template>
	<LayoutCard title="推荐歌单">
		<scroll-view scroll-x="true" class="song-list">
			<view v-for="i in 2" :key="i">
			<SongListItem ></SongListItem>
			<SongListItem></SongListItem>	
			<SongListItem></SongListItem>	
			<SongListItem></SongListItem>	
			<SongListItem></SongListItem>	
			<SongListItem></SongListItem>	
			</view>
		</scroll-view>
	</LayoutCard>
</template>

<script>
import LayoutCard from './LayoutCard.vue';
import SongListItem from './SongListItem.vue';
export default {
	components: {
		LayoutCard,
		SongListItem
	}
};
</script>

<style lang="scss" scoped>
	.song-list {
		white-space: nowrap;
		height: 700rpx;
	}
</style>
