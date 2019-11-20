<template>
	<view>
		
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
					<view class="flexRowBetween font12 ">
						<view class="flex">
							<view class="price fs15 flexEnd">2400</view>
							<view class="fs12 color9 mgl5 mgr10">已售：285</view>
							<view class="fanIcon dian fs12">
								<view class="tt">店返</view>
								<view class="fs10">￥23</view>
							</view>
							<view class="fanIcon tuan  fs12">
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
				is_show:false,
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
	@import "../../assets/style/proList.css";
	
	page{padding-bottom: 50rpx;}
	
</style>
