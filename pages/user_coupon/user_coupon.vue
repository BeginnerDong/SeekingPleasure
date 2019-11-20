<template>
	<view>
		<view class="flexRowBetween orderNav whiteBj color6">
			<view class="tt" :class="curr==1?'on':''" @click="changeCurr('1')">未使用</view>
			<view class="tt" :class="curr==2?'on':''" @click="changeCurr('2')">已使用</view>
			<view class="tt" :class="curr==3?'on':''" @click="changeCurr('3')">已过期</view>
		</view>	
		
		<view class="couponList mglr4" v-show="curr==1">
			<view class="item flexRowBetween" v-for="(item,index) in couponDate" :key="index">
				<view class="ll flexCenter">
					<view class="mny ftw">5</view>
				</view>
				<view class="rr fs12">
					<view class="fs15 ftw">优惠券</view>
					<view class="pdtb5">无门槛使用</view>
					<view>使用时间：2019.11.11-2019.11.18</view>
				</view>
			</view>
		</view>
		
		<view class="couponList mglr4" v-show="curr==2">
			<view class="item flexRowBetween itemUse" v-for="(item,index) in couponDate" :key="index">
				<view class="FXLabel fs12">已使用</view>
				<view class="ll flexCenter">
					<view class="mny ftw">5</view>
				</view>
				<view class="rr fs12">
					<view class="fs15 ftw">优惠券</view>
					<view class="pdtb5">无门槛使用</view>
					<view>使用时间：2019.11.11-2019.11.18</view>
				</view>
			</view>
		</view>
		<view class="couponList mglr4" v-show="curr==3">
			<view class="item flexRowBetween itemUse" v-for="(item,index) in couponDate" :key="index">
				<view class="FXLabel fs12">已过期</view>
				<view class="ll flexCenter">
					<view class="mny ftw">5</view>
				</view>
				<view class="rr fs12">
					<view class="fs15 ftw">优惠券</view>
					<view class="pdtb5">无门槛使用</view>
					<view>使用时间：2019.11.11-2019.11.18</view>
				</view>
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				Router:this.$Router,
				showView: false,
				is_show:false,
				wx_info: {},
				curr:1,
				couponDate:[{},{},{}]
			}
		},

		onLoad(options) {
			uni.setStorageSync('canClick', true);
		},
		methods: {
			changeCurr(curr){
				const self = this;
				if(curr!=self.curr){
					self.curr=curr
				}
			},
			getMainData() {
				const self = this;
				self.$apis.userGet(postData, callback);
			}
		}
	}
</script>

<style>
	@import "../../assets/style/NavTab.css";
	
	.orderNav .tt{width:33.3%}
	.couponList .item{height: 200rpx;padding: 20rpx 0;background: url(../../static/images/coupons-img.png) no-repeat 0 0/100% 100%;box-sizing: border-box;position: relative;margin-top: 30rpx;border-radius: 10rpx;overflow: hidden;box-shadow: 0 0 16rpx rgba(68,68,68,0.1);}
	.couponList .item .ll{width: 29%;padding: 0 20rpx;box-sizing: border-box;}
	.couponList .item .ll .mny{font-size: 100rpx; color: #ff2121;}
	.couponList .item .ll .mny:before{content: '￥';font-size: 28rpx; padding-right: 10rpx; font-weight: normal;}
	.couponList .item .rr{ width: 71%; height: 140rpx;box-sizing: border-box;padding: 0 30rpx;border-left: 1px dashed #3799FA;}
	.couponList .item.itemUse{background-image: url(../../static/images/coupons-img1.png);}
	
	.couponList .FXLabel{width: 100rpx;height: 100rpx;border-radius: 50%;border:1px solid #b7b7b7;text-align: center;line-height: 120rpx;position: absolute; top: -20rpx;right: -20rpx;transform: rotate(45deg);}
	
</style>
