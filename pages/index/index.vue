<template name="RecommendSong">
	<view class="content">
		<uni-search-bar v-model="searchValue" @confirm="search" placeholder="搜索你喜欢的音乐" />
		<u-swiper :list="swiperList" @click="clickSwiper" previousMargin="30" nextMargin="30" circular :autoplay="true" radius="5" :indicator="true"></u-swiper>
		<recommend-song :songList="recommendSongList" />
		<SongList :songList="songList"></SongList>
		<RankList :rankList="rankList"></RankList>
		<pure-player></pure-player>
	</view>
</template>

<script>
import RecommendSong from '../../component/RecommendSong.vue';
import SongList from '../../component/SongList.vue'
import RankList from '../../component/RankList.vue'
import PurePlayer from '../../component/player.vue'
export default {
	components: {
		RecommendSong,
		SongList,
		RankList,
		PurePlayer
	},
	data() {
		return {
			searchValue: '',
			swiperList: [],
			recommendSongList: [],
			songList: [
				[{
						cover: 'url',
						description: '毛不易 | 唱尽人生百态'
					},
					{
						cover: 'url',
						description: '毛不易 | 唱尽人生百态'
					},
					{
						cover: 'url',
						description: '毛不易 | 唱尽人生百态'
					},
					{
						cover: 'url',
						description: '毛不易 | 唱尽人生百态'
					},
					{
						cover: 'url',
						description: '毛不易 | 唱尽人生百态'
					},
					{
						cover: 'url',
						description: '毛不易 | 唱尽人生百态'
					}
				],
				[{
						cover: 'url',
						description: '你知道不知道'
					},
					{
						cover: 'url',
						description: '你知道不知道'
					},
					{
						cover: 'url',
						description: '你知道不知道'
					},
					{
						cover: 'url',
						description: '你知道不知道'
					},
					{
						cover: 'url',
						description: '你知道不知道'
					},
					{
						cover: 'url',
						description: '你知道不知道'
					}


				]
			],
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

		};
	},
	async onLoad() {
		this.getBanner()
		this.getRecommendSongs()
	},
	methods: {
		search(value) {
			console.log(value);
		},
		clickSwiper(index) {
			console.log(index);
		},
		async getBanner() {
			let res = await uni.$u.http.get('http://localhost:3000/home/banner')
			res.data.forEach((item) => {
				this.swiperList.push(item.pic)
			})
			console.log(this.swiperList)
		},
		async getRecommendSongs() {
			function arrTrans(num, arr) {
				const songList = []
				arr.forEach((item, index) => {
					const page = Math.floor(index / num)
					if(!songList[page]) {
						songList[page] = []
					}
					songList[page].push(item)
				})
				return songList
			}
			let res = await uni.$u.http.get('http://localhost:3000/home/recommend-songs')
			console.log(res)
			this.recommendSongList = arrTrans(3, res.data)
			console.log(this.recommendSongList)
		}
	}
};
</script>

<style lang="scss" scoped>
.content {
	height: 100vh;

	.swiper-item {
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
	}
}
</style>
