<template>
	<view>
		<!-- 搜索 -->
		<view class="flexRowBetween seachbox">
			<view class="flex" >
				<span class="Gps fs12 avoidOverflow">西安市</span>
				<image class="mgl5" style="width: 14rpx; height: 8rpx;" src="../../static/images/home-icon1.png" />
			</view>
			<view class="flexRowBetween rr">
				<button class="seachBtn" type="button"></button>
				<view class="input">
					<input type="text" name="" value="" placeholder="搜索" />
				</view>
			</view>
		</view>
		
		<!-- 首页分类导航 -->
		<view class="indHome pdlr4 flex pdb15">
			<swiper class="swiper-box" indicator-dots="true"  indicator-active-color="#3799fa">
				<swiper-item class="swiper-item flex" style="flex-wrap: wrap;">
					<view class="item"  @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon3.png"></image>
						<view class="tit">美食</view>
					</view>
					<view class="item" @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon4.png"></image>
						<view class="tit">KTV</view>
					</view>
					<view class="item" @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon5.png"></image>
						<view class="tit">休闲生活</view>
					</view>
					<view class="item" @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon6.png"></image>
						<view class="tit">酒店入住</view>
					</view>
					<view class="item" @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon7.png"></image>
						<view class="tit">饮料</view>
					</view>
					<view class="item" @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon8.png"></image>
						<view class="tit">学习培训</view>
					</view>
					<view class="item" @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon9.png"></image>
						<view class="tit">母婴亲子</view>
					</view>
					<view class="item" @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon10.png"></image>
						<view class="tit">保养爱车</view>
					</view>
				</swiper-item>
				<swiper-item class="swiper-item flex" style="flex-wrap: wrap;">
					<view class="item" @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon5.png"></image>
						<view class="tit">休闲生活</view>
					</view>
					<view class="item" @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon7.png"></image>
						<view class="tit">饮料</view>
					</view>
					<view class="item" @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon8.png"></image>
						<view class="tit">学习培训</view>
					</view>
					<view class="item" @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon9.png"></image>
						<view class="tit">母婴亲子</view>
					</view>
					<view class="item" @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon10.png"></image>
						<view class="tit">保养爱车</view>
					</view>
					<view class="item" @click="Router.navigateTo({route:{path:'/pages/fineFood/fineFood'}})">
						<image src="../../static/images/home-icon6.png"></image>
						<view class="tit">酒店入住</view>
					</view>
				</swiper-item>
				
			</swiper>
		</view>
		
		<view class="pdb15">
			<image style="width: 686rpx;height: 129rpx;display: block;margin: 0 auto;" src="../../static/images/home-img.png" mode=""></image>
		</view>
		
		<!-- banner -->
		<view class="index_topBj pdlr4">
			<view class="banner-box">
				<view class="banner">
					<swiper class="swiper-box flex" indicator-dots="true" autoplay="true" interval="3000" duration="1000"  indicator-active-color="#3799fa">
						<block v-for="(item,index) in labelData" :key="index">
							<swiper-item class="swiper-item">
								<image :src="item" class="slide-image"/>
							</swiper-item>
						</block>
					</swiper>
				</view>
			</view>
		</view>
		
		<view class="ftw pdlr4 mgt15 fs15">推荐</view>
		<view class="proList flexRowBetween pdlr4">
			<view class="item-lis pr" v-for="(item,index) in produtList" :key="index" @click="Router.navigateTo({route:{path:'/pages/proDetail/proDetail'}})">
				<view class="fixLable">热销</view>
				<view class="pr">
					<image class="img" src="../../static/images/home-img4.png" alt="" />
					<view class="fs12 rr flexCenter countdown white">
						<view>距结束仅剩</view>
						<uni-countdown font-color="#fff" bgr-color="red" timer="2019-12-23 12:00:00" :day="1" :hour="2" :minute="30" :second="0"></uni-countdown>
					</view>
				</view>
				<view class="infor">
					<view class="tit avoidOverflow3">[西安·牛背梁]国家级森林公园，世界生物圈保护区，仅298元=2达人1小抢牛背梁套票~享含双床房1晚+门票2张+双早+免费停车！</view>
					<view class="flex">
						<view class="price fs15 flexEnd">2400</view>
						<view class="fs12 color9 mgl5 mgr10">已售：285</view>
					</view>
					<view class="flexRowBetween font12 mgt10">
						<view class="flex">
							<view class="fanIcon dian fs12">
								<view class="tt">店返</view>
								<view class="fs10">￥23</view>
							</view>
							<view class="fanIcon tuan fs12">
								<view class="tt">团返</view>
								<view class="fs10">￥23</view>
							</view>
						</view>
						<view class="fs15 font10 Rposter">海报</view>
					</view>
					
				</view>
			</view>
		</view>
		
		<!--底部tab键-->
		<view class="navbar">
			<view class="navbar_item" @click="Router.redirectTo({route:{path:'/pages/index/index'}})">
				<view class="nav_img">
					<image src="../../static/images/nabar1-a.png" />
				</view>
				<view class="text this-text">首页</view>
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
					<image src="../../static/images/nabar5.png" />
				</view>
				<view class="text">我的</view>
			</view>
		</view>
		<!--底部tab键 end-->
		
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
					"../../static/images/home-img1.png",
					"../../static/images/home-img2.png",
					"../../static/images/home-img3.png",
				],
				produtList:[{},{},{},{}]
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
	@import "../../assets/style/navbar.css";
	@import "../../assets/style/proList.css";
	page{padding-bottom: 160rpx;}
	
	.seachbox{padding: 30rpx 4%;box-sizing: border-box;}
	.seachbox .Gps{max-width: 100rpx;}
	.seachbox .Licon{width:26rpx; height:26rpx; display: block;}
	.seachbox .rr{width: 75%;background:#F5F5F5;border-radius: 8rpx;overflow: hidden;}
	.seachbox .rr .input{width: 85%;}
	.seachbox .rr .input input{width: 100%;line-height: 60rpx;border-radius: 40rpx;padding: 0 20rpx 0 0px;box-sizing: border-box;display: block;border: none;}
	.seachbox .rr .seachBtn{width: 15%;height: 60rpx; display: block;background: url(../../static/images/home-icon2.png) no-repeat center center/32rpx 32rpx;border: none;}
	
	
	/* 分类导航 */
	.indHome{ flex-wrap:wrap;}
	.indHome .item{width: 25%;text-align: center;padding-bottom: 15px; font-size: 24rpx; color: #222;display: flex; flex-direction: column;}
	.indHome .item image {width:50rpx;height: 50rpx; border-radius: 50%;margin-bottom: 20rpx;margin: 0 auto 10rpx auto; }
	
	.swiper-box {height: 320rpx;box-sizing: border-box; width: 100%;}
	.swiper-box swiper-item {width: 100%/* important;left:auto!important;margin: 0 30rpx; position: initial!important;float: left; */}
	.swiper-box image {width: 100%;height: 100%;}
	

	
</style>
