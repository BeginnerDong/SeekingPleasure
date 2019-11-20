<template>
	<view>
		<view class="pdlr4 borderB1">
			<view class="ftw fs16 pdtb15">关注店铺</view>
			<view class="typeSelt flex fs15 " >
				<view class="item" :class="curr==index?'on':''" @click="changeCurr(index)" v-for="(item,index) in shopDate" :key="index">{{item}}</view>
			</view>
		</view>
		
		<view class="pdlr4 borderB1">
			<view class="ftw fs16 pdtb15">关注类型</view>
			<view class="typeSelt flex fs15 " >
				<view class="item" :class="currType==index?'on':''" @click="changeType(index)" v-for="(item,index) in typeDate" :key="index">{{item}}</view>
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
				curr:0,
				shopDate:['探鱼','胖哥两','海底捞','奈雪的茶','星巴克','麦当劳','长安大排档','探鱼','肯德基','小六汤包','京管涮'],
				currType:0,
				typeDate:['美食','酒店入住','饮料','母婴亲子','KTV','别墅','民宿','迪士尼','民宿','酒店','景点门票','海边','儿童乐园']
			}
		},
		
		onLoad(options) {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			changeCurr(index){
				const self = this;
				self.curr = index
			},
			changeType(index){
				const self = this;
				self.currType = index
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
