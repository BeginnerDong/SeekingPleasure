<template>
	<view>
		<view class="interct_idexLis pdlr4">
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
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				Router:this.$Router,
				showView: false,
				wx_info:{},
				pingjiaDate:[{},{},{},{}]
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
	@import "../../assets/style/pingjia.css";
	@import "../../assets/style/star.css";
</style>
