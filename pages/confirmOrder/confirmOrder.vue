<template>
	<view class="pdlr4">
		<!-- 订单描述 -->
		<view class="whiteBj radius8 mgt15 pdlr4">
			<view class="fs13 color6 pdtb10">订单描述</view>
			<view class="">[西安·牛背梁]国家级森林公园，世界生物圈保护区，仅298元=2达人1小抢牛背梁套票~享含双床房1晚+门票2张+双早+免费停车！</view>
			<view class="flexRowBetween pdtb10">
				<view class="guigeBJ center fs13 color6">规格</view>
				<view class="guigeBJ_rr fs13 color6">[西安]柞水牛背梁景区+牛背梁假日酒店套餐抢购：298元</view>
			</view>
		</view>
		
		<!-- 订单联系人 -->
		<view class="whiteBj radius8 mgt15 pdlr4">
			<view class="fs13 color6 pdt10">订单联系人</view>
			<view class="editLine mgt5">
				<view class="item flexRowBetween pdtb15 borderB1">
					<view class="ll flex"><text class="red">*</text>姓名：</view>
					<view class="rr">张三</view>
				</view>
				<view class="item flexRowBetween pdtb15">
					<view class="ll flex"><text class="red">*</text>手机：</view>
					<view class="rr"><input type="number" maxlength="11" value="" placeholder="请输入手机号" /></view>
				</view>
			</view>
		</view>
		
		<!--  -->
		<view class="whiteBj radius8 mgt15 pdlr4">
			<view class="editLine">
				<view class="item flexRowBetween pdtb15 borderB1">
					<view class="ll">购买数量：</view>
					<view class="rr flex">
						<view class="numBox flex">
							<view @click="counter('-')">-</view>
							<view class="num pubColor">{{count}}</view>
							<view @click="counter('+')">+</view>
						</view>
					</view>
				</view>
				<view class="item flexRowBetween pdtb15">
					<view class="ll">备注：</view>
					<view class="rr"><input type="number" maxlength="11" value="" placeholder="请输入备注" /></view>
				</view>
			</view>
		</view>
		
		<view class="whiteBj radius8 mgt15 pdlr4">
			<view class="myRowBetween">
				<view class="item flexRowBetween pdtb15 borderB1">
					<view class="ll">支付方式：</view>
					<view class="rr flexEnd">微信支付<image class="arrowR" src="../../static/images/about-icon11.png" mode=""></image></view>
				</view>
				<view class="item flexRowBetween pdtb15">
					<view class="ll">优惠券：</view>
					<view class="rr color9 flexEnd">暂无优惠券<image class="arrowR" src="../../static/images/about-icon11.png" mode=""></image></view>
				</view>
			</view>
		</view>
		
		<!-- 底部菜单按钮 -->
		<view class="xqbotomBar flexRowBetween pdl10">
			<view class="left flex">
				<view class="fs12 mgr5">总计</view><view class="price fs15">66.6</view>
			</view>
			<view class="payBtn fs16 white">去支付</view>
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
				count:1
			}
		},
		
		onLoad(options) {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			
			counter(type) {
				const self = this;			
				if (type == '+') {
					self.count++;
				} else {
					if (self.count > 1) {
						self.count--;
					}
				};			
				self.countTotalPrice();
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
	@import "../../assets/style/proDetail.css";
	@import "../../assets/style/editInfor.css";
	page{padding-bottom: 140rpx;background: #F5F5F5;}
	
	.guigeBJ{width: 120rpx;line-height: 60rpx;background: #f5f5f5;border-radius: 40rpx;}
	.guigeBJ_rr{width: 77%;}
	
	.editLine .item{align-items: center;}
	
	/* 数量加减 */
	.numBox{border:2rpx solid #e7e7e7;border-radius: 8rpx;}
	.numBox view{ width: 60rpx; height: 60rpx; line-height: 60rpx; color: #999; font-size:36rpx; text-align: center; }
	.numBox view.num{ width: 100rpx; color: #333; font-size: 28rpx;border-left:1px solid #eee;border-right:1px solid #eee;}
	
</style>
