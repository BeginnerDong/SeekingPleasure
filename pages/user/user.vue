<template>
	<view>
		<view class="user-head flexRowBetween whiteBj">
			<view class="L">
				<image class="us-photo mgb5" src="../../static/images/about-img.png" mode=""></image>
				<view class="avoidOverflow fs13">多啦A梦</view>
			</view>
			<view class="R flex fs13">
				<view class="item flex" @click="Router.navigateTo({route:{path:'/pages/user_address/user_address'}})">
					<image class="icon" src="../../static/images/about-icon.png" mode=""></image>
					<view>地址管理</view>
				</view>
				<view class="item flex" @click="Router.navigateTo({route:{path:'/pages/user_coupon/user_coupon'}})">
					<image class="icon" src="../../static/images/about-icon1.png" mode=""></image>
					<view>我的优惠券</view>
				</view>
				<view class="item flex">
					<image class="icon" src="../../static/images/about-icon2.png" mode=""></image>
					<view>设置</view>
				</view>
				<view class="item flex" @click="Router.navigateTo({route:{path:'/pages/user_course/user_course'}})">
					<image class="icon" src="../../static/images/about-icon3.png" mode=""></image>
					<view>使用教程</view>
				</view>
			</view>
		</view>
		<view class="f5H5"></view>
		<view class="pdlr4 whiteBj">
			<view class="userNav flexRowBetween pdtb15 fs13">
				<view class="item flexColumn"  @click="Router.navigateTo({route:{path:'/pages/user_serveOrder/user_serveOrder'}})">
					<image src="../../static/images/about-icon4.png"></image>
					<view class="tit">服务订单</view>
				</view>
				<view class="item" @click="Router.navigateTo({route:{path:'/pages/user_wuliuOrder/user_wuliuOrder'}})">
					<image src="../../static/images/about-icon5.png"></image>
					<view class="tit">物流订单</view>
				</view>
				<view class="item" @click="Router.navigateTo({route:{path:'/pages/user_pinOrder/user_pinOrder'}})">
					<image src="../../static/images/about-icon6.png"></image>
					<view class="tit">拼团订单</view>
				</view>
			</view>
		</view>
		
		<view class="userOrder mglr4">
			<view class="item radius8 whiteBj mgt15">
				<view class="fixIcon"><image src="../../static/images/about-icon7.png" mode=""></image></view>
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
						<view class="ewm" @click="ewxShow"><image src="../../static/images/about-img2.png" mode=""></image></view>
					</view>
				</view>
			</view>
			
			<view class="item radius8 whiteBj mgt15">
				<view class="fixIcon"><image src="../../static/images/about-icon8.png" mode=""></image></view>
				<view class="flexRowBetween fs12">
					<view class=" color9">交易时间：2019-11-19</view>
					<view class="red">已发货</view>
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
				<view class="fixIcon"><image src="../../static/images/about-icon9.png" mode=""></image></view>
				<view class="flexRowBetween fs12">
					<view class=" color9">交易时间：2019-11-19</view>
					<view class="red">已开团</view>
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
						<view class="pubColor pdlr4 fs13">还差一人成团成功</view>
					</view>
				</view>
			</view>
		</view>
		
		<!-- 二维码弹框 -->
		<view class="black-bj" v-show="is_show"></view>
		<view class="ewxShow whiteBj" v-show="is_show">
			<view class="colseBtn fs20" style="top: auto;bottom: -100rpx;" @click="ewxShow">×</view>
			<view><image src="../../static/images/about-img2.png" mode="widthFix"></image></view>
		</view>
		
		<!--底部tab键-->
		<view class="navbar" style="box-shadow:none;">
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/index/index'}})">
				<view class="nav_img">
					<image src="../../static/images/nabar1.png" />
				</view>
				<view class="text">首页</view>
			</view>
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/pin/pin'}})" >
				<view class="nav_img">
					<image src="../../static/images/nabar2.png" />
				</view>
				<view class="text">拼</view>
			</view>
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/car/car'}})" >
				<view class="nav_img">
					<image src="../../static/images/nabar3.png" />
				</view>
				<view class="text">购物车</view>
			</view>
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/follow/follow'}})">
				<view class="nav_img">
					<image src="../../static/images/nabar4.png" />
				</view>
				<view class="text">关注</view>
			</view>
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/user/user'}})">
				<view class="nav_img">
					<image src="../../static/images/nabar5-a.png" />
				</view>
				<view class="text this-text">我的</view>
			</view>
		</view>
		<!--底部tab键 end-->
		
		
		
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
			ewxShow(){
				const self = this;
				self.is_show = !self.is_show
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
	@import "../../assets/style/navbar.css";
	@import "../../assets/style/userOrder.css";
	page{padding-bottom: 140rpx;background: #F5F5F5;}
	
	.user-head{padding: 40rpx 2% 40rpx 6%;}
	.user-head .us-photo{width: 100rpx;height: 100rpx;display: block;}
	.user-head .L{width: 28%;}
	.user-head .R{display: flex;flex-wrap: wrap; width: 65%;}
	.user-head .R .item{width: 50%;padding: 16rpx 0;}
	.user-head .R .item .icon{width: 30rpx;height: 30rpx;margin-right: 10rpx;}
	
	/* 分类导航 */
	.userNav .item{width: 33.3%;text-align: center;}
	.userNav .item image {width:50rpx;height: 50rpx;margin-bottom: 20rpx;margin: 0 auto 10rpx auto; }
	
</style>
