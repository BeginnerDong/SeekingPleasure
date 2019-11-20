<template>
	<view>
		
		<view class="pdlr4 xqInfor">
			<view class="center titile fs16">玩转吃喝玩乐分享达人功能：佣金提现、邀请好友、分享产品</view>
			<view class="center fs13 color9 pdb15">2019-11-20</view>
			
			<view class="xqInfor">
				<image src="../../static/images/shezhi-img.png" mode="widthFix"></image>
			</view>
			<view class="pdtb15 fs13 color9">阅读2.8万</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				Router:this.$Router,
				wx_info: {},
			}
		},
		onLoad(options) {
			uni.setStorageSync('canClick', true);
		},
		methods: {
			getMainData() {
				const self = this;
				self.$apis.userGet(postData, callback);
			}
		}
	}
</script>

<style>
	@import "../../assets/style/NavTab.css";
	.xqInfor image{width: 100%;max-width: 100%;display: block;margin: 0 auto;}
	.titile{line-height: 48rpx;padding: 40rpx 20rpx 30rpx 20rpx;}
</style>
