<template>
	<view>
		<view class="pdlr4 borderB1">
			<view class="ftw fs16 pdtb15">关注店铺</view>
			<view class="typeSelt flex fs15 " >
				<view class="item" :class="{on:item.bOn}" @click="changeCurr(index)" v-for="(item,index) in shopDate" :key="index">{{item.title}}</view>
			</view>
		</view>
		
		<view class="pdlr4 borderB1">
			<view class="ftw fs16 pdtb15">关注类型</view>
			<view class="typeSelt flex fs15 ">
				<view class="item" :class="{on:item.bOn}" @click="changeType(index)" v-for="(item,index) in typeDate" :key="index">{{item.title}}</view>
			</view>
			
		</view>
		
		<view class="submitbtn mgt30">
			<view class="btn">保存</view>
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
				shopDate:[
					{title:"探鱼",bOn:false},
					{title:"胖哥两",bOn:false},
					{title:"海底捞",bOn:false},
					{title:"奈雪的茶",bOn:false},
					{title:"星巴克",bOn:false},
					{title:"麦当劳",bOn:false},
					{title:"长安大排档",bOn:false},
					{title:"探鱼",bOn:false},
					{title:"肯德基",bOn:false},
					{title:"小六汤包",bOn:false},
					{title:"京管涮",bOn:false}
				],
				typeDate:[
					{title:"美食",bOn:false},
					{title:"酒店入住",bOn:false},
					{title:"饮料",bOn:false},
					{title:"母婴亲子",bOn:false},
					{title:"KTV",bOn:false},
					{title:"别墅",bOn:false},
					{title:"迪士尼",bOn:false},
					{title:"民宿",bOn:false},
					{title:"酒店",bOn:false},
					{title:"景点门票",bOn:false},
					{title:"海边",bOn:false},
					{title:"儿童乐园",bOn:false}
				]
			}
		},
		
		onLoad(options) {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			changeCurr(i){
				const self = this;
				self.shopDate[i].bOn = !self.shopDate[i].bOn;
			},
			changeType(i){
				const self = this;
				self.typeDate[i].bOn = !self.typeDate[i].bOn;
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
	.typeSelt{flex-wrap: wrap;}
	.typeSelt .item{padding: 0 24rpx;line-height: 60rpx;border-radius: 35rpx;border:1px solid #eee;margin: 0 20rpx 40rpx 0;}
	.typeSelt .item.on{background: linear-gradient(to right,#ff995a,#fc7532);color: #fff;}
</style>
