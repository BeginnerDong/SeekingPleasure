<template>
	<view>
		<view class="orderNav pdlr4 flexRowBetween fs14 borderB1 whiteBj">
			<view class="tt" :class="curr==1?'on':''" @click="changeCurr('1')">推荐</view>
			<view class="tt" :class="curr==2?'on':''" @click="changeCurr('2')">活动</view>
			<view class="tt flexCenter" :class="curr==3?'on':''" @click="changeCurr('3')">区域<image class="nav_arrowB" :src="curr==3?'../../static/images/home-icon01.png':'../../static/images/home-icon02.png'" mode=""></image></view>
			<view class="tt flexCenter" :class="curr==4?'on':''" @click="changeCurr('4')">分类<image class="nav_arrowB" :src="curr==4?'../../static/images/home-icon01.png':'../../static/images/home-icon02.png'" mode=""></image></view>
		</view>
		
		<view class="proList flexRowBetween pdlr4" style="margin-top: 82rpx;">
			<view class="item-lis pr" v-for="(item,index) in produtList" :key="index" @click="Router.navigateTo({route:{path:'/pages/pinDetail/pinDetail'}})">
				<view class="fixLable">出去玩</view>
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
		
		<view class="black-bj" v-show="curr==3"></view>
		<view class="black-bj2" v-show="curr==4"></view>
		
		<!-- 区域选择 -->
		<view class="quyuNav fs12 whiteBj" v-show="curr==3">
			<view class="fs13 pdb20">距我最近</view>
			<view class="fs12 pdb10">指定区域</view>
			<view class="quCont">
				<view class="item flex" v-for="(item,index) in quContData" :key="index" >
					<view class="ll flex" :class="quyuTit==index?'on':''" @click="quyuNav(index)">{{item.title}}</view>
					<view class="rr flexRowBetween" @click="addrsTex(index)">
						<view>{{item.text}}</view>
						<image class="selt" :src="currAdrs==index?'../../static/images/home-icon03.png':''" mode=""></image>
					</view>
				</view>
			</view>
		</view>
		
		<!-- 分类导航选择 -->
		<view class="pdlr4 fenleiNav fs12 flex pdt20 whiteBj" v-show="'curr==4',''">
			<view class="item" v-for="(item,index) in fenleiDaTa" :key="index" :class="num==index?'on':''" @click="changeNum(index)">{{item}}</view>
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
					<image src="../../static/images/nabar2-a.png" />
				</view>
				<view class="text this-text">拼</view>
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
				curr:1,
				num:0,
				is_show:false,
				is_fenleiNav:false,
				fenleiDaTa:["美食","酒店入住","饮料","母婴亲子","KTV","别墅","民宿","迪士尼","酒店","景点门票","海边","儿童乐园"],
				produtList:[{},{},{},{}],
				quContData:[
					{title:'雁塔区',text:'高新大都荟'},
					{title:'碑林区',text:'高新大都荟'},
					{title:'长安区',text:'高新大都荟'},
					{title:'莲湖区',text:'高新大都荟'},
				],
				quyuTit:0,
				currAdrs:0,
				hghghg:false
			}
		},
		
		onLoad(options) {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			changeCurr(curr){
				const self=this;
				if(curr!=self.curr){
					self.curr=curr
				}
			},
			changeNum(index){
				const self=this;
				self.num = index
			},
			quyuNav(index){
				const self=this;
				self.quyuTit = index
			},
			addrsTex(index){
				const self=this;
				self.currAdrs = index
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
	
	page{padding-bottom: 160rpx;background: #F5F5F5;}
	.orderNav{width: 100%;box-sizing: border-box;position: fixed;z-index: 82; top: 82rpx;left: 0;}
	.nav_arrowB{width:14rpx; height: 8rpx; display: block;margin-left: 10rpx;}
	
	/* 区域选择 */
	.quyuNav{width: 100%;box-sizing: border-box;flex-wrap: wrap;position: fixed; top: 156rpx; left:0;z-index: 83;border-top: 1px solid #eee;padding: 40rpx 4%;}
	.quyuNav .quCont .item{line-height: 70rpx;}
	.quyuNav .quCont .ll{width: 20%;border-right: 1px solid #eee;color: #999;box-sizing: border-box;}
	.quyuNav .quCont .item .ll.on{color: #222;}
	.quyuNav .quCont .rr{padding-left:20rpx ; width: 80%;box-sizing: border-box;}
	.quyuNav .quCont .rr .selt{width: 26rpx;height: 19rpx; display: block;}
	
	/* 分类导航选择 */
	.fenleiNav{ width: 100%;box-sizing: border-box;flex-wrap: wrap;position: fixed; top: 156rpx; left:0;z-index: 83;border-top: 1px solid #eee;}
	.fenleiNav .item{line-height: 60rpx;border-radius: 30rpx;padding: 0 30rpx;border: 1px solid #eee;margin-right: 20rpx;margin-bottom: 40rpx;}
	.fenleiNav .item.on{background: #fc7633;color: #fff;}
</style>
