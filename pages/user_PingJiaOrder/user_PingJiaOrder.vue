<template>
	<view>
		<view class="userOrder mglr4">
			<view class="item radius8 whiteBj mgt15">
				<view class="flexRowBetween fs12">
					<view class=" color9">交易时间：2019-11-19</view>
					<view class="red">已收货</view>
				</view>
				<view class="flexRowBetween infor pdtb10 dashedB1">
					<view class="Lpic">
						<image src="../../static/images/about-img1.png" mode=""></image>
					</view>
					<view class="R_text avoidOverflow4 fs13">[西安·牛背梁]国家级森林公园，世界生物圈保护区，仅298元=2达人1小抢牛背梁套票~享含双床房1晚+门票2张+双早+免费停车！</view>
				</view>
				<view class="flex pdt15">
					<view class="red">￥59.00</view>
					<view class="fs12 color9 mgl5 mgr10">双人餐</view>
					<view class="pubColor fs13">×1</view>
				</view>
			</view>
		</view>
		
		<view class="mglr4 whiteBj radius8 mgt15 pdlr4">
			<view class="pdtb15 flex borderB1">
				<view class="mgr10">总体</view>
				<view class="starBox mgr5">
					<image src="../../static/images/focus-on-icon1.png" mode=""></image>
					<image src="../../static/images/focus-on-icon1.png" mode=""></image>
					<image src="../../static/images/focus-on-icon1.png" mode=""></image>
					<image src="../../static/images/focus-on-icon1.png" mode=""></image>
					<image src="../../static/images/focus-on-icon1.png" mode=""></image>
				</view>
			</view>
			<view>
				<textarea class="fs12" value="" placeholder="说几句,让更多小伙伴了解我" />
			</view>
			<view class="upPic flex pdb10">
				<view class="item"><image src="../../static/images/camera.png" mode=""></image></view>
			</view>
		</view>
		
		<view class="submitbtn mgt30">
			<view class="btn">发表</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				Router:this.$Router,
				showView: false,
				wx_info:{},
				is_show:false
			}
		},
		
		onLoad(options) {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			getMainData() {
				const self = this;
				console.log('852369')
				const postData = {};
				postData.tokenFuncName = 'getProjectToken';
				self.$apis.orderGet(postData, callback);
			}
		}
	};
</script>

<style>
	@import "../../assets/style/userOrder.css";
	@import "../../assets/style/star.css";
	page{padding-bottom: 60rpx;background: #F5F5F5;}
	.dashedB1{border-bottom: 1px dashed #eee;}
	
	.starBox image{width: 28rpx;height: 28rpx;margin-right: 8rpx;}
	textarea{padding: 30rpx 0;box-sizing: border-box;width: 100%;display: block;height: 240rpx;}
	.upPic{flex-wrap: wrap;}
	.upPic .item{width: 120rpx;height: 120rpx;display: block; padding-bottom: 20rpx;}
	.upPic .item image{width: 100%;height: 100%;display: block;border-radius: 8rpx;}
</style>
