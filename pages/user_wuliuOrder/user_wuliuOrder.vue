<template>
	<view>
		<view class="flexRowBetween orderNav whiteBj color6">
			<view class="tt" :class="curr==1?'on':''" @click="changeCurr('1')">全部</view>
			<view class="tt" :class="curr==2?'on':''" @click="changeCurr('2')">待发货</view>
			<view class="tt" :class="curr==3?'on':''" @click="changeCurr('3')">已发货</view>
			<view class="tt" :class="curr==4?'on':''" @click="changeCurr('4')">已收货</view>
			<view class="tt" :class="curr==5?'on':''" @click="changeCurr('5')">其他</view>
		</view>
		
		<view class="userOrder mglr4">
			<view class="item radius8 whiteBj mgt15">
				<view class="flexRowBetween fs12">
					<view class=" color9">交易时间：2019-11-19</view>
					<view class="red">未使用</view>
				</view>
				<view class="flexRowBetween infor pdtb10">
					<view class="Lpic">
						<image src="../../static/images/about-img1.png" mode=""></image>
					</view>
					<view class="R_text avoidOverflow4 fs13">[西安·牛背梁]国家级森林公园，世界生物圈保护区，仅298元=2达人1小抢牛背梁套票~享含双床房1晚+门票2张+双早+免费停车！</view>
				</view>
				<view class="flexRowBetween pdtb10 adrs">
					<view class="flex fs13 color6">
						<image class="icon mgr10" src="../../static/images/about-icon10.png" mode=""></image>
						<view class="tex">陕西省西安市雁塔区高新大都荟</view>
					</view>
					<view class="flexEnd"><image class="arrowR" src="../../static/images/about-icon11.png" mode=""></image></view>
				</view>
				<view class="pdt20 flexRowBetween twoCont">
					<view class="half flexColumn">
						<view class="Tbtn fs12 mgb20">双人餐</view>
						<view class="red">￥59.00 <text class="pubColor fs13 mgl10">×1</text></view>
					</view>
					<view class="half flexColumn">
						<view class="okBtn">确认收货</view>
					</view>
				</view>
			</view>
			
			<view class="item radius8 whiteBj mgt15">
				<view class="flexRowBetween fs12">
					<view class=" color9">交易时间：2019-11-19</view>
					<view class="red">未使用</view>
				</view>
				<view class="flexRowBetween infor pdtb10">
					<view class="Lpic">
						<image src="../../static/images/about-img1.png" mode=""></image>
					</view>
					<view class="R_text avoidOverflow4 fs13">[西安·牛背梁]国家级森林公园，世界生物圈保护区，仅298元=2达人1小抢牛背梁套票~享含双床房1晚+门票2张+双早+免费停车！</view>
				</view>
				<view class="flexRowBetween pdtb10 adrs">
					<view class="flex fs13 color6">
						<image class="icon mgr10" src="../../static/images/about-icon10.png" mode=""></image>
						<view class="tex">陕西省西安市雁塔区高新大都荟</view>
					</view>
					<view class="flexEnd"><image class="arrowR" src="../../static/images/about-icon11.png" mode=""></image></view>
				</view>
				<view class="pdt20 flexRowBetween twoCont">
					<view class="half flexColumn">
						<view class="Tbtn fs12 mgb20">双人餐</view>
						<view class="red">￥59.00 <text class="pubColor fs13 mgl10">×1</text></view>
					</view>
					<view class="half flexColumn">
						<view class="okBtn" @click="Router.navigateTo({route:{path:'/pages/user_PingJiaOrder/user_PingJiaOrder'}})">去评价</view>
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
				Router:this.$Router,
				showView: false,
				wx_info:{},
				is_show:false,
				curr:1
			}
		},
		
		onLoad(options) {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
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
				console.log('852369')
				const postData = {};
				postData.tokenFuncName = 'getProjectToken';
				self.$apis.orderGet(postData, callback);
			}
		}
	};
</script>

<style>
	@import "../../assets/style/NavTab.css";
	@import "../../assets/style/userOrder.css";
	page{padding-bottom: 60rpx;background: #F5F5F5;}
	.orderNav .tt{width: 20%;}
</style>
