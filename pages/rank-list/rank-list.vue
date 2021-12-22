<template>
	<view class="rank-list">
		<rank-item v-for="(item, index) in rankList" :rankTitle="item.rankTitle" :song="item.song"></rank-item>
	</view>
</template>

<script>
	import RankItem from '../../component/RankItem.vue'
	export default {
		components: {
			RankItem
		},
		data() {
			return {
				rankList: [{
						rankTitle: '新歌榜',
						cover: 'url',
						song: [{
								name: '无名的人',
								singer: '毛不易'
							},
							{
								name: '无名的人',
								singer: '毛不易'
							},
							{
								name: '无名的人',
								singer: '毛不易'
							}
						]
					},
					{
						rankTitle: '新歌榜',
						cover: 'url',
						song: [{
								name: '无名的人',
								singer: '毛不易'
							},
							{
								name: '无名的人',
								singer: '毛不易'
							},
							{
								name: '无名的人',
								singer: '毛不易'
							}
						]
					},
					{
						rankTitle: '新歌榜',
						cover: 'url',
						song: [{
								name: '无名的人',
								singer: '毛不易'
							},
							{
								name: '无名的人',
								singer: '毛不易'
							},
							{
								name: '无名的人',
								singer: '毛不易'
							}
						]
					},
				]

			}
		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.rank-list {
		margin-left: 30rpx;
	}
</style>
