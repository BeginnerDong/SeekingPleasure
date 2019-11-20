<template>
	<view>
		
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
				proListDate:[{},{},{},{},{},{},{}]
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
	@import "../../assets/style/car.css";
	page{padding-bottom: 60rpx;}
	/* 店铺商品 */
	.shopOrder .item .link{width: 85%;}
	.shopOrder .item .ll .pic{width: 260rpx;height: 160rpx;}
	.shopOrder .item .ll .lable{position: absolute;top:30rpx;left: 0;line-height: 40rpx;padding: 0 16rpx;color: #fff;background: rgba(0,0,0,0.5);border-radius: 0 20rpx 20rpx 0;font-size: 24rpx;}
	.shopOrder .item .rr{height: 160rpx;}
	.R-addCar{width: 15%;}
	.R-addCar image{width: 36rpx;height: 36rpx; display: block;margin-top: 110rpx;}
	.lookAll-btn{width: 180rpx;line-height: 50rpx;border-radius: 30rpx;border:1px solid #eee;}
	

</style>
