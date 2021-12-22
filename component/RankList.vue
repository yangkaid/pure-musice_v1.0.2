<template>
	<LayoutCard title="排行榜">
		<view class="rank">
			<RankItem v-for="(item, index) in rankList" :rankTitle="item.rankTitle" :song="item.song"></RankItem>
		</view>
	</LayoutCard>
</template>

<script>
import LayoutCard from './LayoutCard.vue';
import RankItem from './RankItem.vue';
export default {
	components: {
		LayoutCard,
		RankItem
	},
	props: {
		rankList: {
			type: Array,
			default: []
		},
	},
};
</script>

<style lang="scss" scoped>
	.rank {
		width: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
</style>
