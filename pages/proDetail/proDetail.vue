<template>
	<view>
		
		<!-- banner -->
		<view class="detailxqBan">
			<swiper class="swiper-box flex" indicator-dots="true" autoplay="true" interval="3000" duration="1000"  indicator-active-color="#ff5420">
				<block v-for="(item,index) in labelData" :key="index">
					<swiper-item class="swiper-item">
						<image :src="item" class="slide-image"/>
					</swiper-item>
				</block>
			</swiper>
		</view>
		<view class="flexRowBetween countdown white">
			<view>限时抢购</view>
			<view class="fs12 rr flexEnd">距结束仅剩
			<uni-countdown font-color="#ff5420" bgr-color="#fff" timer="2019-12-23 12:00:00" :day="1" :hour="2" :minute="30" :second="0"></uni-countdown></view>
		</view>
		
		<view class="detail_one">
			<view class="ftw">麻辣小龙虾</view>
			<view class="flexRowBetween fs12 color6">
				<view class="flex mgt5 adrs">
					<image style="width: 20rpx;height: 26rpx;margin-right: 10rpx;" src="../../static/images/details-icon2.png" mode=""></image>
					<view class="adrs-tit">探鱼(西安大都荟店)</view>
				</view>
				<view class="flexEnd range fs13">266m</view>
			</view>
			<view class="flex mgt15">
				<view class="price ftw fs16 mgr15">129</view>
				<view class="fanIcon dian fs12">
					<view class="tt">店返</view>
					<view class="fs10">￥23</view>
				</view>
				<view class="fanIcon tuan fs12">
					<view class="tt">团返</view>
					<view class="fs10">￥23</view>
				</view>
			</view>
		</view>
		<view class="f5H5"></view>
		
		<view class="flexRowBetween mglr4 pdtb15" @click="Router.navigateTo({route:{path:'/pages/shopDetail/shopDetail'}})">
			<view class="flex fs13">
				<image src="../../static/images/details-icon.png" style="width: 30rpx;height: 27rpx;margin-right: 10rpx;" mode=""></image>
				<text style="width: 580rpx;">探鱼(西安大都荟店)</text>
			</view>
			<view>
				<image class="arrowR" src="../../static/images/about-icon11.png" mode=""></image>
			</view>
		</view>
		
		
		<!-- 规格选择 -->
		<view class="f5H5"></view>
		<view class="mglr4 pdtb15">
			<view class="ftw mgb10">规格选择</view>
			<view class=" selt_specs color6">
				<scroll-view class="list" scroll-x>
					<view class="item" :class="specsNum==index?'on':''" @click="changeSpecs(index)" v-for="(item,index) in specsDate" :key="index" >
						<view class="item-tit">{{item.title}}</view>
						<view class="item-price">{{item.price}}</view>
					</view>
				</scroll-view>
			</view>
		</view>
		<view class="f5H5"></view>
		<view class="flexRowBetween pdlr4 orderNav borderB1">
			<view class="tt" :class="curr==1?'on':''" @click="changeCurr('1')">产品详情</view>
			<view class="tt" :class="curr==2?'on':''" @click="changeCurr('2')">使用说明</view>
		</view>
		
		<view class="mglr4 pdtb15" v-show="curr==1">
			<view class="ftw mgb10">图文介绍</view>
			<view class="xqInfor">
				<view class="cont">
					<view>
						<image src="../../static/images/details-img1.png" mode="widthFix"></image>
					</view>
				</view>
			</view>
		</view>
		
		<view v-show="curr==2">
			<view class="mglr4 pdtb15">
				<view class="ftw mgb10">产品</view>
				<view class="xqInfor">
					<view class="cont">
						<view style="font-size: 30rpx;">【西安】29层云顶餐厅吃五星自助~仅178=2大2小抢悦豪自助餐~海鲜烧烤的餐惬盛宴~使用期到7月底！菜品丰富！吃到扶墙走！</view>
					</view>
				</view>
			</view>
			<view class="f5H5"></view>
			
			<view class="mglr4 pdtb15">
				<view class="ftw mgb10">规格</view>
				<view class="xqInfor">
					<view class="cont color6">178元</view>
				</view>
			</view>
			<view class="f5H5"></view>
			
			<view class="mglr4 pdtb15">
				<view class="ftw mgb10">温馨提示</view>
				<view class="wx_tips">
					<view class="item fs13 color6 pdb10 flex">
						<text class="ll"><view class="dian"></view></text>
						<view class="rr">内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容</view>
					</view>
					<view class="item fs13 color6 pdb10 flex">
						<text class="ll"><view class="dian"></view></text>
						<view class="rr">内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容</view>
					</view>
					<view class="item fs13 color6 pdb10 flex">
						<text class="ll"><view class="dian"></view></text>
						<view class="rr">内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容</view>
					</view>
				</view>
			</view>
		</view>
		
		<!-- 底部菜单按钮 -->
		<view class="xqbotomBar flexRowBetween">
			<view class="left flexRowBetween">
				<view class="ite" @click="Router.navigateTo({route:{path:'/pages/index/index'}})">
					<image src="../../static/images/details-icon3.png" mode=""></image>
					<view>首页</view>
				</view>
				<view class="ite">
					<image src="../../static/images/details-icon4.png" mode=""></image>
					<view>客服</view>
				</view>
				<view class="ite">
					<image src="../../static/images/details-icon5.png" mode=""></image>
					<view>加入购物车</view>
				</view>
			</view>
			<view class="payBtn fs16 white" @click="Router.navigateTo({route:{path:'/pages/confirmOrder/confirmOrder'}})">立即抢购</view>
		</view>
		
	</view>
</template>

<script>
	import uniCountdown from "@/components/uni-countdown/uni-countdown.vue";
	
	export default {
		components: {
			uniCountdown
		},
		data() {
			return {
				Router:this.$Router,
				showView: false,
				wx_info:{},
				labelData: [
					"../../static/images/details-img.png",
					"../../static/images/details-img.png",
				],
				curr:1,
				specsNum:0,
				specsDate:[
					{title:'双人套餐',price:'178元'},
					{title:'单人套餐',price:'178元'},
					{title:'家庭套餐',price:'178元'},
					{title:'双人套餐',price:'178元'}
				]
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
			changeSpecs(index){
				const self = this;
				self.specsNum = index
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
	@import "../../assets/style/proList.css";
	@import "../../assets/style/proDetail.css";
	page{padding-bottom: 120rpx;}
	.orderNav .tt{width: 50%;}
</style>
