<template>
	<view>
		<view class="top-tools-container">
			<uni-search-bar :radius="100" @confirm="search"></uni-search-bar>
			<view class="condition-container">
				<view class="example-body">
					<uni-datetime-picker v-model="range" type="daterange" @maskClick="maskClick" />
				</view>
				<view class="more">
					更多
					<uni-icons type="bottom"></uni-icons>
				</view>
			</view>
		</view>

		<view class="list-container" >
			<view class="item-container" v-for="(item, index) in feedList" @click="toDetail(item.feedId)" >
				<view class="img-box">
					<image class="face-img" :src="item.imgUrl" mode=""></image>
				</view>
				<view class="infor-box">
					<view class="title-div">
						{{item.title}}
					</view>
					<view class="description-div">
						{{item.description}}
					</view>
					<text></text>
					<view class="place-time-div">
						<text> {{item.foundPlace}} </text>
						<text style="float: right;"> {{(new Date(item.updateTime).getFullYear()) + '/' + (new Date(item.updateTime).getMonth() + 1) + '/' + (new Date(item.updateTime).getDate())}} </text>
					</view>
				</view>
			</view>
		</view>


	</view>
</template>

<script>
	export default {
		data() {
			return {
				range: '',
				feedList: [{
						feedId: 1,
						imgUrl: '../../static/logo.png',
						title: '钥匙圈',
						description: '是个冰墩墩，在二操场发现的，发现时候已经湿透了',
						foundPlace: '二操场南面',
						updateTime: 1649751332805
					},
					{
						feedId: 2,
						imgUrl: '../../static/logo.png',
						title: '钥匙圈',
						description: '是个冰墩墩，在二操场发现的，发现时候已经湿透了',
						foundPlace: '二操场南面',
						updateTime: 1649751332805
					},
					{
						feedId: 3,
						imgUrl: '../../static/logo.png',
						title: '钥匙圈',
						description: '是个冰墩墩，在二操场发现的，发现时候已经湿透了',
						foundPlace: '二操场南面',
						updateTime: 1649751332805
					},
					{
						feedId: 4,
						imgUrl: '../../static/logo.png',
						title: '钥匙圈',
						description: '是个冰墩墩，在二操场发现的，发现时候已经湿透了',
						foundPlace: '二操场南面',
						updateTime: 1649751332805
					}
				]
			};
		},
		onLoad() {
			console.log(1)
		},
		methods: {
			toDetail(feedId) {
				uni.navigateTo({
					url: 'lost-detail?feedId=' + feedId
				});
			}
		}
	}
</script>

<style lang="scss">
	
	.list-container {
		background-color: #efefef;
	}
	
	.item-container {
		margin: 0rpx 30rpx 50rpx 30rpx;
		background-color: #ffffff;
		display: flex;
		box-shadow: 10rpx 10rpx 10rpx #b1b1b1;
		
		
		.infor-box {
			padding: 30rpx 20rpx;
			display: flex;
			flex-direction: column;
			font-size: 28rpx;
			.title-div {
				font-weight: 600;
			}
			
			.description-div {
				width: 340rpx;
				overflow: hidden;
				text-overflow: ellipsis;
				white-space: nowrap;
			}
			
			.place-time-div {
				margin-top: auto;
			}
		}

		.face-img {
			width: 300rpx;
			height: 250rpx;
		}
	}

	.top-tools-container {
		background-color: #efefef;
		padding-bottom: 50rpx;
	}

	.condition-container {
		display: flex;
		margin: 0 20rpx;
	}


	.more {
		background-color: #ffffff;
		font-size: 28rpx;
		color: #808080;
		// padding: 5rpx 0;
		margin: 0 0 0 40rpx;
		width: 200rpx;
		height: 80rpx;
		line-height: 80rpx;
		text-align: center;
		// height: 100px;
	}
</style>
