<template>
	<view>
		<view class="pdlr4 whiteBj whiteBj">
			<view class="flexRowBetween pdt15 pdb10">
				<view class="flex fwOneNav fs15">
					<view :class="num==1?'on':''" @click="changeNum('1')">类别</view>
					<view class="mgl25" :class="num==2?'on':''" @click="changeNum('2')">店铺</view>
				</view>
				<view class="pubColor flexEnd fs13" @click="Router.navigateTo({route:{path:'/pages/followType/followType'}})"><image style="width: 32rpx;height: 27rpx;margin-right: 10rpx;" src="../../static/images/focus-on-icon5.png" mode=""></image>关注类型</view>
			</view>
		</view>
		
		<view v-show="num==1">
			<view class="pdlr4 whiteBj">
				<view class="orderNav fs13 flex pdt5 color6 borderB1">
					<view class="tt" :class="curr==index?'on':''" @click="changeCurr(index)" v-for="(item,index) in sallNav" :key="index">{{item}}</view>
				</view>
			</view>
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
		</view>
		
		<view class="whiteBj" v-show="num==2">
			<view class="pdlr4">
				<view class="orderNav fs13 flex pdt5 color6 borderB1">
					<view class="tt" :class="shopCurr==index?'on':''" @click="changeShopCurr(index)" v-for="(item,index) in shopNav" :key="index">{{item}}</view>
				</view>
			</view>
			<view class="shopList">
				<view class="item flexRowBetween" v-for="(item,index) in shopList" :key="index" @click="Router.navigateTo({route:{path:'/pages/shopDetail/shopDetail'}})">
					<view class="ll">
						<image class="pic" src="../../static/images/focus-on-img.png" mode=""></image>
					</view>
					<view class="rr">
						<view class="infor flexRowBetween">
							<view class="L_cont">
								<view class="avoidOverflow">探鱼(西安大都荟店)</view>
								<view class="flex pdtb5 fs12">
									<view class="starBox mgr5">
										<image src="../../static/images/focus-on-icon.png" mode=""></image>
										<image src="../../static/images/focus-on-icon.png" mode=""></image>
										<image src="../../static/images/focus-on-icon.png" mode=""></image>
										<image src="../../static/images/focus-on-icon.png" mode=""></image>
										<image src="../../static/images/focus-on-icon1.png" mode=""></image>
									</view>
									<view>￥54/人</view>
								</view>
								<view class="fs11 color6">香锅/烤鱼 南二环西段</view>
							</view>
							<view class="R_num">
								<view class="flexEnd pubColor">
									<image class="gzIcon" src="../../static/images/focus-on-icon4.png" mode=""></image>
									<view>关注</view>
								</view>
								<view class="flexEnd pdtb5"><view class="end_time fs12 color9">营业至21:00</view></view>
								<view class="flexEnd fs12">215m</view>
							</view>
						</view>
						
						<view class="pdtb10 borderB1 flex"><view class="hotLable fs10">雁塔区香锅烤鱼热门榜第1名</view></view>
						<view class="fs11 color6 flexRowBetween pdt10">
							<image class="quanIcon" src="../../static/images/focus-on-icon2.png" mode=""></image>
							<view class="">￥69</view>
							<view class="yuanJia">￥100</view>
							<view class="quan_text avoidOverflow">100元代金券 (周内午市可使用)</view>
						</view>
						<view class="fs11 color6 flexRowBetween pdt10">
							<image class="quanIcon" src="../../static/images/focus-on-icon2.png" mode=""></image>
							<view class="">￥69</view>
							<view class="yuanJia">￥100</view>
							<view class="quan_text avoidOverflow">100元代金券 (周内午市可使用)</view>
						</view>
					</view>
				</view>
			</view>
			
		</view>
		
		<!--底部tab键-->
		<view class="navbar">
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
					<image src="../../static/images/nabar4-a.png" />
				</view>
				<view class="text this-text">关注</view>
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
				curr:0,
				sallNav:['全部','饮品','酒店入住','KTV','母婴亲子'],
				is_show:false,
				produtList:[{},{},{},{}],
				num:1,
				shopCurr:0,
				shopNav:['全部','酒店类','海边','KTV','别墅'],
				shopList:[{},{},{}]
			}
		},
		
		onLoad(options) {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			changeNum(num){
				const self = this;
				if(num!=self.num){
					self.num = num
				}
			},
			changeCurr(index){
				const self = this;
				self.curr = index
			},
			changeShopCurr(index){
				const self = this;
				self.shopCurr = index
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
	@import "../../assets/style/NavTab.css";
	@import "../../assets/style/proList.css";
	@import "../../assets/style/star.css";
	
	page{padding-bottom: 140rpx;background: #F5F5F5;}
	.orderNav .tt{width: auto; margin-right: 40rpx; line-height: 40rpx;padding-bottom:20rpx;}
	.nav_arrowB{width:14rpx; height: 8rpx; display: block;margin-left: 10rpx;}
	.fwOneNav .on{color: #3799FA;}
	.shopList .item{align-items: flex-start;padding: 30rpx 4%;border-bottom: 10rpx solid #F5F5F5;}
	.shopList .item .ll{width: 30%;}
	.shopList .item .ll .pic{width: 180rpx; height: 180rpx;display: block;}
	.shopList .item .rr{width: 70%;}
	.shopList .item .rr .L_cont{width: 62%;}
	.shopList .item .rr .R_num{width: 38%;}
	.shopList .item .rr .gzIcon{width: 24rpx;height: 24rpx; display: block;margin-right: 10rpx;}
	.shopList .item .rr .quanIcon{width: 30rpx;height:30rpx; display: block;}
	.shopList .item .rr .quan_text{width: 60%;}
	.shopList .item .end_time{line-height: 40rpx;padding: 0 8rpx;border: 1px solid #eee;border-radius: 6rpx;}
	.shopList .item .hotLable{line-height: 40rpx;padding: 0 10rpx;background: #ffeae4;border-radius: 6rpx;color: #ff5622;}


</style>
