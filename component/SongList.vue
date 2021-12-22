<template>
	<LayoutCard title="推荐歌单" jumpPage="pages/album-list/album-list">
		<scroll-view scroll-x="true" class="song-list">
			<view v-for="(item,index1) in songList">
				<SongListItem v-for="(list,index2) in item" :description="list.description"></SongListItem>
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
		},
		props: {
			songList: {
				type: Array,
				default: []
			},
		},
	};
</script>

<style lang="scss" scoped>
	.song-list {
		white-space: nowrap;
	}
</style>
