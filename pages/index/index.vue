<template name="RecommendSong">
	<view class="content">
		<uni-search-bar v-model="searchValue" @confirm="search" />
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
			<swiper-item v-for="item in swiperList" :key="item.name">
				<view class="swiper-item " :style="{ backgroudColor: item.bgColor }" @click="seeCover(item)">
					{{ item.name }}
					<!-- <image :src="item.url" mode=""widthFix></image> -->
				</view>
			</swiper-item>
		</swiper>
		<recommend-song />
		<SongList></SongList>
		<RankList></RankList>
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
			searchValue: 'Hello',
			swiperList: [
				{
					name: 'A',
					bgColor: 'red'
				},
				{
					name: 'B',
					bgColor: 'green'
				},
				{
					name: 'C',
					bgColor: 'pink'
				}
			]
		};
	},
	onLoad() {},
	methods: {
		search(value) {
			console.log(value);
		},
		seeCover(item) {
			console.log(item);
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
