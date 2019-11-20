<template>
	<view class="pdlr4">
		
		<view class="shopOrder mgt15 whiteBj radius8">
			<view class="flex pdtb15"><view class="mgl10 mgr5"><image class="shopIcon" src="../../static/images/shopping-icon.png" mode=""></image></view>
				<view class="fs13">小六汤包</view>
			</view>
			<view class="item pr flexRowBetween pdb15" v-for="(item,index) in proListDate" :key="index">
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
							<view class="flexEnd fs13 color9">×1</view>
						</view>
					</view>
				</view>
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
				<view class="item flexRowBetween pdtb15">
					<view class="ll">备注：</view>
					<view class="rr"><input type="number" maxlength="11" value="" placeholder="请输入备注" /></view>
				</view>
			</view>
		</view>
		
		<view class="whiteBj radius8 mgt15 pdlr4">
			<view class="myRowBetween">
				<view class="item flexRowBetween pdtb15 borderB1">
					<view class="ll">购买数量：</view>
					<view class="rr flexEnd">微信支付<image class="arrowR" src="../../static/images/about-icon11.png" mode=""></image></view>
				</view>
				<view class="item flexRowBetween pdtb15">
					<view class="ll">优惠券：</view>
					<view class="rr color9 flexEnd">暂无优惠券使用<image class="arrowR" src="../../static/images/about-icon11.png" mode=""></image></view>
				</view>
			</view>
		</view>
		
		<!-- 底部菜单按钮 -->
		<view class="xqbotomBar flexRowBetween pdl10">
			<view class="left flexEnd">
				<view class="fs13 color9 mgr10">共2件</view>
				<view class="fs12 mgr5">总计</view><view class="price fs15">36.00</view>
			</view>
			<view class="payBtn fs14 white">提交订单</view>
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
				proListDate:[
					{price:'59.00',count:'1'},
					{price:'59.00',count:'1'}
				],
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
	@import "../../assets/style/proDetail.css";
	@import "../../assets/style/editInfor.css";
	@import "../../assets/style/car.css";
	page{padding-bottom: 140rpx;background: #F5F5F5;}
	
	.editLine .item{align-items: center;}
	.shopOrder .R_cont{width: 100%;}
	
</style>
