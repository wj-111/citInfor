<template>
	<view>
		<view class="user-top-container">
			<view class="avatar-box">
				<image class="avatar-img" :src="userInfo.userAvatar" mode=""></image>
			</view>
			<view class="user-name-box">
				{{userInfo.userName}}
				18030721
			</view>
			<view class="contact-box tools-button">
				联系
				<uni-icons type="chat" size="20"></uni-icons>
			</view>
			<view class="share-box tools-button">
				分享
				<uni-icons type="paperplane" size="20"></uni-icons>
			</view>
		</view>

		<view class="title-box">
			标题：{{feedInfo.title}}
		</view>
		<view class="some-info-box">
			分区：
			<view class="partition-box">
				电子产品
			</view>
			<view class="" style="margin-left: auto;">
				发布时间：{{(new Date(feedInfo.publishTime).getMonth() + 1) + '/' + (new Date(feedInfo.publishTime).getDate()) + ' ' + (new Date(feedInfo.publishTime).getHours()) + ':' + (new Date(feedInfo.publishTime).getMinutes())}}
			</view>
		</view>

		<swiper class="swiper" indicator-dots="true">
			<swiper-item>
				<image class="swiper-img" :src="userInfo.userAvatar" mode=""></image>
			</swiper-item>
			<swiper-item>
				<image class="swiper-img" :src="userInfo.userAvatar" mode=""></image>
			</swiper-item>
			<swiper-item>
				<image class="swiper-img" :src="userInfo.userAvatar" mode=""></image>
			</swiper-item>
		</swiper>
		
		<view class="description-box">
			{{feedInfo.description}}
		</view>
		
		<view class="found-time-box other-info-box">
			发现时间
			{{(new Date(feedInfo.publishTime).getMonth() + 1) + '/' + (new Date(feedInfo.publishTime).getDate()) + ' ' + (new Date(feedInfo.publishTime).getHours()) + ':' + (new Date(feedInfo.publishTime).getMinutes())}}
		</view>
		
		<view class="found-place-box other-info-box">
			发现地点
			{{feedInfo.foundPlace}}
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				userInfo: {
					userName: '学生1',
					userAvatar: '../../static/logo.png'
				},
				feedInfo: {
					title: 'macbook笔记本',
					publishTime: 1649751332805,
					description: '文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述,\
						文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述,\
						文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述文本描述,\
					',
					foundPlace: '二操场南侧'
				},
			};
		},
		onLoad: function (option) {
			console.log(option.feedId);
		}
	}
</script>

<style lang="scss">
	.user-top-container {
		display: flex;
		align-items: center;
		padding: 30rpx;

		.avatar-img {
			width: 150rpx;
			height: 150rpx;
			border-radius: 50%;
		}

		.contact-box {
			margin-left: auto;
		}

		.share-box {
			margin: 0rpx 30rpx;
		}

		.tools-button {
			background-color: #00aaff;
			width: 120rpx;
			height: 80rpx;
			border-radius: 10rpx;
			line-height: 80rpx;
			text-align: center;
		}
	}


	.title-box {
		font-weight: 600;
		font-size: 36rpx;
		margin: 20rpx;
	}


	.some-info-box {
		display: flex;
		margin: 20rpx;

		.partition-box {}
	}

	.swiper-img {
		width: 100%;
		height: 100%;
	}

	.swiper {
		height: 400rpx;
	}
	
	.description-box {
		margin: 20rpx;
	}
	
	
	.other-info-box {
		margin: 20rpx;
	}
</style>
