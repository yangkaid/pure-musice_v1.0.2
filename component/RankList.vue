<template>
	<LayoutCard title="排行榜">
		<view class="rank">
			<RankItem></RankItem>
			<RankItem></RankItem>
			<RankItem></RankItem>
			<RankItem></RankItem>
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
	}
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
