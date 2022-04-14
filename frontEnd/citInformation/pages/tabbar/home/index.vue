<template>
	<view class="content">
		
			<navigator url="/pages/lost/lost-list" hover-class="navigator-hover">
				<view class="region" style="background-color: #aaffff;">
					失物招领
				</view>
			</navigator>
		
		<view class="region" style="background-color: #00aaff;">
			闲置买卖
		</view>
		<view class="region" style="background-color: #aaff7f;">
			吐槽论坛
		</view>
		<view class="region" style="background-color: #ffaaff;">
			寻ta专区
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			title: 'Hello'
		};
	},
	onLoad() {},
	methods: {}
};
</script>

<style>
.content {
	text-align: center;
	/* height: 400rpx; */
	/* margin-top: 200rpx; */
	display: flex;
	flex-direction: column;
	padding: 20rpx;
}
.region {
	height: 200rpx;
	margin: 30rpx;
	line-height: 200rpx;
	font-size: 42rpx;
	border-radius: 20rpx;
	box-shadow: 10rpx 10rpx 10rpx #b1b1b1;
}
</style>
