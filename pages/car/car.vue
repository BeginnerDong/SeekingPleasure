<template>
	<view>
		
		<view class="">
			<view class="mglr4 pdtb15 flexRowBetween">
				<view>全部宝贝(3)</view>
				<view class="fs13"  v-show="!is_allDelt" @click="allDeltShow">管理</view>
				<view class="fs13"  v-show="is_allDelt" @click="allDeltShow">完成</view>
			</view>
			
			<view class="shopOrder mglr4 mgb15 whiteBj radius8">
				<view class="flex pdtb15">
					<view><image class="seltIcon" src="../../static/images/shopping-icon2.png" mode=""></image></view>
					<view class="mgl10 mgr5"><image class="shopIcon" src="../../static/images/shopping-icon.png" mode=""></image></view>
					<view class="fs13">小六汤包</view>
				</view>
				<view class="item pr flexRowBetween pdb15" v-for="(item,index) in proListDate" :key="index">
					<view class="item_selBtn flex">
						<image class="seltIcon" src="../../static/images/shopping-icon2.png" mode=""></image>
					</view>
					<view class="R_cont flexRowBetween">
						<view class="ll">
							<image class="pic" src="../../static/images/shopping-img.png" mode=""></image>
						</view>
						<view class="rr">
							<view class="titile font15 avoidOverflow2">美味大虾一份</view>
							<view class="flexRowBetween Bmny">
								<view class="flex pubColor font13">
									<view class="price">{{item.price}}</view>
								</view>
								<view class="numBox flex">
									<view @click="counter(index,'-')">-</view>
									<view class="num">{{item.count}}</view>
									<view @click="counter(index,'+')">+</view>
								</view>
							</view>
						</view>
					</view>
				</view>
			</view>
			
			<view class="shopOrder mglr4 mgb15 whiteBj radius8">
				<view class="flex pdtb15">
					<view><image class="seltIcon" src="../../static/images/address-icon1.png" mode=""></image></view>
					<view class="mgl10 mgr5"><image class="shopIcon" src="../../static/images/shopping-icon.png" mode=""></image></view>
					<view class="fs13">小六汤包</view>
				</view>
				<view class="item pr flexRowBetween pdb15" v-for="(item,index) in proListDate" :key="index">
					<view class="item_selBtn flex">
						<image class="seltIcon" src="../../static/images/shopping-icon1.png" mode=""></image>
					</view>
					<view class="R_cont flexRowBetween">
						<view class="ll">
							<image class="pic" src="../../static/images/shopping-img.png" mode=""></image>
						</view>
						<view class="rr">
							<view class="titile font15 avoidOverflow2">美味大虾一份</view>
							<view class="flexRowBetween Bmny">
								<view class="flex pubColor font13">
									<view class="price">{{item.price}}</view>
								</view>
								<view class="numBox flex">
									<view @click="counter(index,'-')">-</view>
									<view class="num">{{item.count}}</view>
									<view @click="counter(index,'+')">+</view>
								</view>
							</view>
						</view>
					</view>
				</view>
			</view>
			
		</view>
		
		
		<!-- 底部结算 -->
		<view class="xqbotomBar flexRowBetween borderB1"  style="bottom: 112rpx;">
			<view class="left flexRowBetween"  style="width: 66%;">
				<view class="flex color6 mgl10">
					<image class="seltIcon mgr5" src="../../static/images/address-icon1.png" mode=""></image>
					全选
				</view>
				<view class="fs13 mgr5 flexEnd">合计<view class="price fs15 mgl5">66.6</view></view>
			</view>
			<view class="payBtn fs16 white" style="width: 34%;"  @click="Router.navigateTo({route:{path:'/pages/confirmOrder/confirmOrder'}})">结算</view>
		</view>
		
		<!-- 底部全选删除 -->
		<view class="xqbotomBar flexRowBetween borderB1" v-show="is_allDelt" style="bottom: 112rpx;z-index: 100;">
			<view class="left flexRowBetween"  style="width: 66%;">
				<view class="flex color6 mgl10">
					<image class="seltIcon mgr5" src="../../static/images/address-icon1.png" mode=""></image>
					全选
				</view>
			</view>
			<view class="pubColor flexEnd mgr15" style="width: 34%;"><view class="alldeltBtn">删除</view></view>
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
					<image src="../../static/images/nabar3-a.png" />
				</view>
				<view class="text this-text">购物车</view>
			</view>
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/follow/follow'}})">
				<view class="nav_img">
					<image src="../../static/images/nabar4.png" />
				</view>
				<view class="text">关注</view>
			</view>
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/user/user'}})">
				<view class="nav_img">
					<image src="../../static/images/nabar5.png" />
				</view>
				<view class="text">我的</view>
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
				is_show:false,
				count:1,
				proListDate:[
					{price:'59.00',count:'1'},
					{price:'59.00',count:'1'}
				],
				is_allDelt:false
			}
		},
		
		onLoad(options) {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			allDeltShow(){
				const self = this;
				self.is_allDelt = !self.is_allDelt
			},
			counter(index,type) {
				const self = this;
				if (type == '+') {
					self.proListDate[index].count++;
				} else {
					if (self.proListDate[index].count > 1) {
						self.proListDate[index].count--;
					}
				};
				self.$Utils.setStorageArray('cartData', self.proListDate[index], 'id', 999);
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
	@import "../../assets/style/navbar.css";
	@import "../../assets/style/proDetail.css";
	@import "../../assets/style/car.css";
	page{padding-bottom: 240rpx;background: #F5F5F5;}
	
</style>
