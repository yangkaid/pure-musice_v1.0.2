<template>
	<view class="album-list">
		<SongListItem v-for="(item, index) in albumList" :key="index" :description="item.description"></SongListItem>
	</view>
</template>

<script>
	import SongListItem from '../../component/SongListItem.vue';
	export default {
		components: {
			SongListItem
		},
		data() {
			return {
				albumList: [{
						cover: 'url',
						description: '文艺书店的英文歌单列表'
					},
					{
						cover: 'url',
						description: '文艺书店的英文歌单列表'
					},
					{
						cover: 'url',
						description: '文艺书店的英文歌单列表'
					},
					{
						cover: 'url',
						description: '文艺书店的英文歌单列表'
					},
					{
						cover: 'url',
						description: '文艺书店的英文歌单列表'
					},
					{
						cover: 'url',
						description: '文艺书店的英文歌单列表'
					}
				]

			}
		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.album-list {
		margin-left: 15rpx;
	}
</style>
