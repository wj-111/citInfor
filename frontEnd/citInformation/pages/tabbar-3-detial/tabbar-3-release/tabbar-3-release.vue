<template>
	<view class="content">
		<view class="title-input-box">
			<input type="text" placeholder="标题" />
		</view>
		<view class="textarea-box">
			<view class="uni-textarea">
				<textarea placeholder="请输入正文描述..." />
			</view>
		</view>

		<view class="img-list-container">
			<view class="upload-img-box" v-for="(item, index) in uploadImgList">
				<image class="img-box" :src="item" mode=""></image>
			</view>

			<view class="img-box add-show-box">
				<view class="">
					<uni-icons type="camera-filled" size="40"></uni-icons>
				</view>
				<view class="">
					照片/视频
				</view>
			</view>
		</view>

		<view class="other-input-box">
			发现地点：
			<input class="input-div" type="text" placeholder="可智能匹配" />
		</view>
		<view class="other-input-box">
			发现时间：
			<!-- <input class="input-div" type="text" placeholder="选择" /> -->
			<!-- <uni-datetime-picker class="input-div" type="datetime" v-model="datetimesingle" @change="changeLog" /> -->
			<picker class="input-div" mode="date" :value="date" @change="bindDateChange">
				<!-- <view class="uni-input">{{date}}</view> -->
				<input :value="date" type="text" placeholder="设置" />
			</picker>

		</view>
		<view class="other-input-box">
			联系信息设置：
			<input class="input-div" type="text" placeholder="设置" />
		</view>
		<view class="other-input-box">
			联系地点（可不填）：
			<input class="input-div" type="text" placeholder="可智能匹配" />
		</view>
		
		<view class="commit-butoon-box">
			<button type="primary">确认发布</button>
		</view>

	</view>
</template>

<script>
	export default {

		data() {

			const currentDate = this.getDate({
				format: true
			});
			
			return {
				title: 'Hello',
				uploadImgList: [
					'../../../static/logo.png',
					'../../../static/logo.png',
					// '../../../static/logo.png'
				],
				date: currentDate,
			}
		},
		onLoad() {

		},
		methods: {
			changeLog() {
				console.log(1)
			},
			bindDateChange: function(e) {
				this.date = e.detail.value
			},
			getDate(type) {
				const date = new Date();
				let year = date.getFullYear();
				let month = date.getMonth() + 1;
				let day = date.getDate();

				if (type === 'start') {
					year = year - 60;
				} else if (type === 'end') {
					year = year + 2;
				}
				month = month > 9 ? month : '0' + month;
				day = day > 9 ? day : '0' + day;
				return `${year}-${month}-${day}`;
			}
		}
	}
</script>

<style lang="scss">
	.content {
		background-color: #efefef;
		padding-bottom: 200rpx;
	}

	.title-input-box {
		background-color: #ffffff;
		/* font-size: 36rpx; */
		padding: 20rpx;
		border-bottom: #bcbcbc 2rpx solid;
	}

	.textarea-box {
		padding: 20rpx;
		background-color: #ffffff;
		height: 200rpx;
		font-size: 16rpx;
	}

	.img-list-container {
		display: flex;
		flex-wrap: wrap;
		background-color: #ffffff;

		.img-box {
			width: 200rpx;
			height: 200rpx;
			margin: 20rpx;
		}

		.add-show-box {
			background-color: #efefef;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
		}
	}



	.other-input-box {
		background-color: #FFFFFF;
		margin: 10rpx 0;
		padding: 20rpx;
		display: flex;
		align-items: center;

		.input-div {
			margin-left: auto;
			padding: 10rpx;
			background-color: #efefef;
		}
	}
	.commit-butoon-box {
		padding: 20rpx;
	}
</style>
