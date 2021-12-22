<template name="RecommendSong">
	<view class="content">
		<uni-search-bar v-model="searchValue" @confirm="search" placeholder="搜索你喜欢的音乐" />
		<u-swiper :list="swiperList" @click="clickSwiper" previousMargin="30" nextMargin="30" circular :autoplay="true"
			radius="5" :indicator="true"></u-swiper>
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
	export default {
		components: {
			RecommendSong,
			SongList,
			RankList
		},
		data() {
			return {
				searchValue: '',
				swiperList: [],
				recommendSongList: [
					[{
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
					[{
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
				],
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
			let res = await uni.$u.http.get('http://localhost:3000/home/banner')
			res.data.forEach((item) => {
				this.swiperList.push(item.pic)
			})
			console.log(this.swiperList)
		},
		methods: {
			search(value) {
				console.log(value);
			},
			clickSwiper(index) {
				console.log(index);
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
