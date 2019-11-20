<template>
	<view>
		
		<view class="detail_join  mglr4">
			<view class="twolist">
				<view class="item flexRowBetween pdt15" v-for="(item,index) in pinList" :key="index">
					<view class="ll flex">
						<view class="photo">
							<image src="../../static/images/about-img.png" mode=""></image>
						</view>
						<view class="tit avoidOverflow">名称名称名称</view>
					</view>
					<view class="rr flexRowBetween">
						<view class="downTime">
							<view class="red fs12">还差1人拼成</view>
							<view class="time">剩余23:23:48</view>
						</view>
						<view class="go"  @click="goPinShow">去拼团</view>
					</view>
				</view>
			</view>
		</view>
		
		
		<!-- 去拼团弹框 -->
		<view class="showSel" v-show="is_goPin">
			<view class="showSelCont fix">
				<view class="colseBtn" @click="goPinShow">×</view>
				<view class="ind_proList">
					<view class="item flexRowBetween" >
						<view class="ll">
							<image src="../../static/images/about-img1.png" mode=""></image>
						</view>
						<view class="rr">
							<view class="avoidOverflow2 title">麻辣小龙虾标题麻辣小龙虾标题麻辣小龙虾标题麻辣小龙虾标题</view>
							<view class="money price">56</view>
						</view>
					</view>
				</view>
				<view class="pdtb15">
					<view class="ftw mgb10">规格选择</view>
					<view class="selt_specs color6 borderB1 pdb10">
						<scroll-view class="list" scroll-x>
							<view class="item" :class="specsNum==index?'on':''" @click="changeSpecs(index)" v-for="(item,index) in specsDate" :key="index" >
								<view class="item-tit">{{item.title}}</view>
								<view class="item-price">{{item.price}}</view>
							</view>
						</scroll-view>
					</view>
				</view>
				
				<view class="submitbtn" style="margin-top: 60rpx;">
					<button class="btn" style="margin-bottom: 0;" type="submit" @click="Router.navigateTo({route:{path:'/pages/confirmOrder/confirmOrder'}})" >确定</button>
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
				specsNum:0,
				specsDate:[
					{title:'双人套餐',price:'178元'},
					{title:'单人套餐',price:'178元'},
					{title:'家庭套餐',price:'178元'},
					{title:'双人套餐',price:'178元'}
				],
				is_goPin:false,
				pinList:[{},{},{},{},{},{}]
			}
		},
		
		onLoad(options) {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			changeSpecs(index){
				const self = this;
				self.specsNum = index
			},
			goPinShow(){
				const self = this;
				self.is_goPin = !self.is_goPin
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
	@import "../../assets/style/proList.css";
	@import "../../assets/style/proDetail.css";
	
</style>
