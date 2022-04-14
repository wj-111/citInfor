<template>
	<view>
		<view class="page">
			<view class="top-tools" style="padding: 20rpx 50rpx; padding-bottom: 0rpx;">
				<view class="left" style="display: inline;"> 
					<uni-icons type="scan" :size="toolsIconSize"></uni-icons>
				</view>
				<view class="right" style="float: right; display: inline;">
					<uni-icons type="chat" :size="toolsIconSize" style="margin-right: 20rpx;"></uni-icons>
					<uni-icons type="gear" :size="toolsIconSize"></uni-icons>
				</view>

			</view>
			<view class="user-info-container">
				<view class="avatar-box">
					<image src="../../../static/logo.png" mode="aspectFit"></image>
				</view>
				<view class="user-text-info-box">
					<view class="name">{{user.name}}</view>
					<view class="no">{{user.no}}</view>
				</view>
			</view>
			
			
			<view class="function-container">
				<view class="function-box">
					<view class="text">
						小程序版本
					</view>
					<view class="arrow">
						<uni-icons type="right" size="30"></uni-icons>
					</view>
				</view>
				
				
				<view class="function-box">
					<view class="text">
						小程序二维码
					</view>
					<view class="arrow">
						<uni-icons type="right" size="30"></uni-icons>
					</view>
				</view>
				<view class="function-box" @click="toMyApplication">
					<view class="text">
						更新日期
					</view>
					<view class="arrow">
						<uni-icons type="right" size="30"></uni-icons>
					</view>
				</view>
				<view class="function-box">
					<view class="text">
						修改密码
					</view>
					<view class="arrow">
						
					</view>
				</view>
			</view>
			<view class="exit-button" @click="test">
				退出
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				toolsIconSize: 32,
				user: {
					name:"吴彦祖",
					no:'18030000'
				},
				icon:{
					size:'16',
					color:'#000000',
					arrowColor:'#969ead'
				}
			}
		},
		onShow() {
			console.log('页面显示');
			try {
			    const value = uni.getStorageSync('userDate');
			    if (value) {
					this.user.name = value.name;
					this.user.no = value.no;
					console.log("更新数据成功");
			    }
			} catch (e) {
				console.log('调用失败');
			}
			
		},
		methods: {
			toMyApplication(){
				uni.navigateTo({url: 'myApplication'});
			},
			test(){
				console.log("初始化")
				
				// try {
				//     const value = uni.getStorageSync('userDate');
				//     if (value) {
				// 		this.user.name = value.name;
				// 		this.user.no = value.no;
				//     }
				// } catch (e) {
				// 	console.log(调用失败)
				// }
				this.user.name = '吴彦祖';
				this.user.no = '18030000';
				uni.clearStorageSync();
			}
		}
	}
</script>

<style lang="scss">
	.page{
		display: flex;
		flex-direction: column;
	}
	
	.user-info-container{
		margin: 20rpx 45rpx;
		display: flex;
		flex-direction: row;
		align-items: center;
		height: 200rpx;
		
		.user-text-info-box{
			line-height: 40rpx;
			margin-left: 20rpx;
			.name{
				font-size: 36rpx;
				margin-bottom: 10rpx;
			}
			.no{
				font-size: 32rpx;
				color: #969799;
			}
		}
		.avatar-box{
			image{
				width: 140rpx;
				height: 140rpx;
				border-radius:50%;
			}
		}
	}
	
	.function-container{
		display: flex;
		flex-direction: column;
		border-top: 1rpx solid #f8f8fb; 
		border-bottom: 1rpx solid #f8f8fb;
		
		.function-box{
			margin: 0 30rpx;
			padding: 0 20rpx;
			display: flex;
			flex-direction: row;
			height: 95rpx;
			font-size: 32rpx;
			align-items: center;
			border-top: 1px solid #F5F5F5; 
			// border-bottom: 1px solid #F9F9F9;
			.icon{
				margin: 0 10rpx;
			}
			.text{
				line-height: 75rpx;
			}
			.arrow{
				margin-left: auto;
			}
		}
	}

	.exit-button{
		margin: 40rpx;
		margin-top: 20rpx;
		// background-color: #007AFF;
		border-style:solid;
		border-width:1rpx;
		border-color: #EEEEEE;
		
		height: 80rpx;
		border-radius: 80rpx;
		text-align: center;
		line-height: 80rpx;
		font-size: 26rpx;
	}

</style>
