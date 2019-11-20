<template>
	<view>
		<view class="pdlr4">
			<view class="fs18 ftw pdt15">呷哺呷哺(西安高新大都荟)</view>
			<view class="flexRowBetween pdtb10">
				<view class="fs12 color9 flex">
					<view class="starBox mgr5">
						<image src="../../static/images/focus-on-icon.png" mode=""></image>
						<image src="../../static/images/focus-on-icon.png" mode=""></image>
						<image src="../../static/images/focus-on-icon.png" mode=""></image>
						<image src="../../static/images/focus-on-icon.png" mode=""></image>
						<image src="../../static/images/focus-on-icon1.png" mode=""></image>
					</view>
					<view>￥54/人<text class="pdl5 pdr5">|</text>火锅店</view>
				</view>
				<view class="flexEnd pubColor" @click="seltFollow">
					<image class="gzIcon mgr5" :src="like?'../../static/images/focus-on-icon3.png':'../../static/images/focus-on-icon4.png'" mode=""></image>
					<view>关注</view>
				</view>
			</view>
			<view class="shop_allimg pr">
				<view class="fix_num fs12 white">共4张</view>
				<scroll-view scroll-x>
					<view class="item"><image src="../../static/images/store-img.png" mode=""></image></view>
					<view class="item"><image src="../../static/images/store-img.png" mode=""></image></view>
					<view class="item"><image src="../../static/images/store-img.png" mode=""></image></view>
					<view class="item"><image src="../../static/images/store-img.png" mode=""></image></view>
				</scroll-view>
			</view>
			<view class="flexRowBetween fs13 shop-betn">
				<image class="samll-Icon mgr5" src="../../static/images/store-icon.png" mode=""></image>
				<view class="flexRowBetween borderB1 rr">
					<view class="avoidOverflow" style="width: 85%">南二环西段火锅热销榜第6名</view>
					<view class="flexEnd"><image class="arrowR" src="../../static/images/store-icon8.png" mode=""></image></view>
				</view>
			</view>
			<view class="flexRowBetween fs13 shop-betn">
				<image class="samll-Icon mgr5" src="../../static/images/store-icon1.png" mode=""></image>
				<view class="borderB1 rr">营业中 | 周一至周日 10:00-22:00</view>
			</view>
			
			<view class="flexRowBetween fs13 shop-betn">
				<image class="samll-Icon mgr5" src="../../static/images/store-icon2.png" style="width: 32rpx;height: 32rpx;" mode=""></image>
				<view class="flexRowBetween borderB1 rr">
					<view class="" style="width: 60%">
						<view>丈八街道高新四路赵家坡村高新大都荟项目第J栋</view>
						<view class="fs12 color6">距您234m</view>
					</view>
					<view class="flexEnd">
						<view class="gpsR-Icon">
							<image src="../../static/images/store-icon3.png" mode=""></image>
						</view>
						<view class="gpsR-Icon">
							<image src="../../static/images/store-icon4.png" mode=""></image>
						</view>
					</view>
				</view>
			</view>
			
			<!-- 买单按钮 -->
			<view class="flexCenter boxShaow radius8 pdtb10 mgb15">
				<image src="../../static/images/store-icon5.png" style="width: 50rpx;height: 50rpx;" mode=""></image>
				<view class="pdl10">买单</view>
			</view>
			
		</view>
		<view class="f5H5"></view>
		<view class="pdlr4">
			<view class="flexRowBetween orderNav">
				<view class="tt" :class="curr==1?'on':''" @click="changeCurr('1')">店铺商品</view>
				<view class="tt" :class="curr==2?'on':''" @click="changeCurr('2')">评价</view>
				<view class="tt" :class="curr==3?'on':''" @click="changeCurr('3')">商家信息</view>
			</view>
		</view>
		
		<view class="fabubtn" @click="Router.navigateTo({route:{path:'/pages/car/car'}})">
			<view class="icon">
				<image src="../../static/images/store-icon7.png" mode=""></image>
			</view>
		</view>
		
		<!-- 店铺商品 -->
		<view class="shopOrder mgt15">
			<view class="item pdb15 flexRowBetween" v-for="(item,index) in proListDate" :key="index">
				<view class="link flexRowBetween" @click="Router.navigateTo({route:{path:'/pages/proDetail/proDetail'}})">
					<view class="ll pr">
						<image class="pic" src="../../static/images/store-img3.png" mode=""></image>
						<view class="lable">招牌菜</view>
					</view>
					<view class="rr">
						<view class="titile font15 avoidOverflow2">美味大虾一份</view>
						<view class="flexRowBetween Bmny">
							<view class="flex pubColor font13">
								<view class="price">129</view>
								<view class="mgl10 color9 fs12">已售235</view>
							</view>
						</view>
					</view>
				</view>
				<view class="R-addCar flexEnd"><image src="../../static/images/store-icon6.png" mode=""></image></view>
			</view>
			<view class="pdtb15 flexCenter" @click="Router.navigateTo({route:{path:'/pages/shopDetail_prodct/shopDetail_prodct'}})">
				<view class="flexCenter lookAll-btn fs12">查看全部 <image class="arrowR" src="../../static/images/store-icon8.png" mode=""></image></view>
			</view>
		</view>
		<view class="f5H5"></view>
		
		<!-- 评价 -->
		<view class="pdlr4">
			<view class="pdt15 ftw">评价(345)</view>
			<view class="interct_idexLis">
				<view class="child" v-for="(item,index) in pingjiaDate" :key="index">
					<view class="flexRowBetween">
						<view class="flex">
							<view class="photo"><image src="../../static/images/store-img1.png" mode=""></image></view>
							<view class="name">
								<view class="fs12 avoidOverflow">快乐的猫</view>
								<view class="color6 fs12">2019-11-19</view>
							</view>
						</view>
						<view class="flexEnd">
							<view class="starBox mgr5">
								<image src="../../static/images/focus-on-icon.png" mode=""></image>
								<image src="../../static/images/focus-on-icon.png" mode=""></image>
								<image src="../../static/images/focus-on-icon.png" mode=""></image>
								<image src="../../static/images/focus-on-icon.png" mode=""></image>
								<image src="../../static/images/focus-on-icon1.png" mode=""></image>
							</view>
						</view>
					</view>
					<view class="fs12 pdtb10">很好吃的鱼在这里，非常好吃，推荐大家去品尝很好吃的鱼在这里，非常好吃。</view>
					<view class="lisThree">
						<view class="item">
							<image src="../../static/images/store-img5.png" mode=""></image>
						</view>
						<view class="item">
							<image src="../../static/images/store-img5.png" mode=""></image>
						</view>
						<view class="item">
							<image src="../../static/images/store-img5.png" mode=""></image>
						</view>
					</view>
				</view>
			</view>
			<view class="pdtb15 flexCenter" @click="Router.navigateTo({route:{path:'/pages/shopDetail_pingjia/shopDetail_pingjia'}})">
				<view class="flexCenter lookAll-btn fs12">查看全部 <image class="arrowR" src="../../static/images/store-icon8.png" mode=""></image></view>
			</view>
		</view>
		<view class="f5H5"></view>
		
		<!-- 商家信息 -->
		<view class="pdlr4">
			<view class="pdt15 ftw">商家信息</view>
			<view class="fs13 color6 pdtb10">就分了的价格哈根flag哈拉嘎嘎监管科撒寄过来人家给感叹号给贴梗海棠让大哥花费案发后及hihi合法化反和范德萨发货后方可卡皇冠假日。</view>
			<view>
				<image style="width: 400rpx;height: 480rpx;" src="../../static/images/store-img2.png" mode=""></image>
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
				curr:1,
				proListDate:[{},{},{}],
				pingjiaDate:[{},{}],
				like:false
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
			seltFollow(){
				const self = this;
				self.like = !self.like
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
	@import "../../assets/style/car.css";
	@import "../../assets/style/star.css";
	@import "../../assets/style/pingjia.css";
	page{padding-bottom: 60rpx;}
	.orderNav .tt{width:33.3%;}
	.gzIcon{width: 24rpx;height: 24rpx;display: block;}
	.samll-Icon{width: 28rpx;height: 28rpx; display: block;}
	.shop_allimg .fix_num{line-height: 40rpx;padding: 0 10rpx;background: rgba(0,0,0,0.5);border-radius: 6rpx;position: absolute; bottom: 40rpx;left: 20rpx; z-index: 2;}
	.shop_allimg scroll-view{white-space: nowrap;}
	.shop_allimg .item{margin-right: 20rpx; display: inline-block;box-sizing: border-box;}
	.shop_allimg .item image{width: 240rpx;height: 160rpx;border-radius: 6rpx;}
	
	.shop-betn{align-items: flex-start; padding-top: 30rpx;}
	.shop-betn .samll-Icon{margin-top: 6rpx;}
	.shop-betn .rr{width: 93%; padding-bottom: 30rpx;border-bottom: 1px solid #eee;}
	.shop-betn:last-child .rr{border-bottom: none;}
	
	.gpsR-Icon{padding: 0 30rpx;}
	.gpsR-Icon:first-child{border-right: 1px solid #eee;}
	.gpsR-Icon image{width: 38rpx;height: 38rpx;display: block;}
	
	/* 店铺商品 */
	.shopOrder .item .link{width: 85%;}
	.shopOrder .item .ll .pic{width: 260rpx;height: 160rpx;}
	.shopOrder .item .ll .lable{position: absolute;top:30rpx;left: 0;line-height: 40rpx;padding: 0 16rpx;color: #fff;background: rgba(0,0,0,0.5);border-radius: 0 20rpx 20rpx 0;font-size: 24rpx;}
	.shopOrder .item .rr{height: 160rpx;}
	.R-addCar{width: 15%;}
	.R-addCar image{width: 36rpx;height: 36rpx; display: block;margin-top: 110rpx;}
	.lookAll-btn{width: 180rpx;line-height: 50rpx;border-radius: 30rpx;border:1px solid #eee;}
	

</style>
