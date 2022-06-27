<template>
	<view class="content">
		
		<view class="head_box">
			<view class="head">
				<image :src="list.src" mode=""></image>
			</view>
			<h3>{{list.class}}</h3>
			<u-notice-bar :text="text1"></u-notice-bar>
			<view class="money">
				<h2>￥{{list.money}}</h2>
				<view class="one">开团价￥{{list.money1}}</view>
				<view class="two">{{list.people}}人已购买本商品</view>
			</view>
			<view class="alert">
				<u-alert :title="title" type = "info" showIcon></u-alert>
			</view>

		</view>
		
		<view class="body" v-for="item in list3" :key="item.id">
			<image :src="item.src" mode=""></image>
		</view>
		
		<view class="foot">
			<view class="left" @click="order">预约开团</view>
			<view class="right">
				<text class="right_middle" @click="Cart">加入购物车</text>
				<text class="right_right" @click="btn">￥{{list.money}}购买</text>
			</view>

		</view>
		<u-modal :show="show"
		 ref="uModal"
		 :closeOnClickOverlay='true'
		 :showConfirmButton='false'
		  :asyncClose="true"
		  width='350rpx'
		  @close='close'>已加入购物车</u-modal>
		<!-- </view> -->
		<u-modal :show="show1"
			 ref="uModal"
			 :closeOnClickOverlay='true'
			 :showConfirmButton='false'
			  :asyncClose="true"
			  width='350rpx'
			  @close='close'>已预约成功</u-modal>
		
		<u-popup :show="show2" 
		mode="bottom"  
		@close="close" 
		:closeable='true' closeIconPos='top-right'>
			<view class="show2">
				<text></text>
			</view>
		</u-popup>
		</view>

	

</template>

<script>
	export default {
		data() {
			return {
				show: false,
				show1: false,
				show2: false,
				title:'有130人参与评论',
				text1:'2022.07.12号开团，请提前预约开团',
				list:
					{
						src: 'http://mms2.baidu.com/it/u=3290724860,3578281849&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=500',
					    class: "探病慰问生日鲜花爱情鲜花问候长辈12枝向日葵",
					    money: "99.9",
					    money1: "59.9",
						people:"134",
					    // go: "去购买"
					},
				list3:[
					{
						id:1,
						src: 'http://mms2.baidu.com/it/u=3290724860,3578281849&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=500',
					},
					{
						id:2,
						src: 'http://mms2.baidu.com/it/u=3290724860,3578281849&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=500',
					},
					{
						id:3,
						src: 'http://mms2.baidu.com/it/u=3290724860,3578281849&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=500',
					},
					{
						id:4,
						src: 'http://mms2.baidu.com/it/u=3290724860,3578281849&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=500',
					},
				]
				
			}
		},
		methods: {
			// 
			Cart(){
				this.show = true
			},
				
			order(){				
				this.show1 = true
			},
			// 
			btn(){
				uni.navigateTo({
					url:"/pages/payment/payment"
				})
				// this.show2 = true
			},
			// 
			close() {
			  this.show = false
			  this.show1 = false
			  this.show2 = false
			},
			
			
		}
	}
</script>

<style lang="scss">
.content{
	width: 100%;
	padding-bottom:calc(var(-–window-bottom)+30rpx);
	// height: 100vh;
}
.head_box{
	width: 95%;
	height: 1000rpx;
	margin: 30rpx auto;
	// background-color: #ff666e;
	// margin-top: 0;
	.alert{
		margin-top: 20rpx;
	}
	.head{
		// width: 100%;
		margin: 0 auto;
		height: 670rpx;
		background-color: #fff;

		image{
			width: 100%;
			height: 100%;
		}
	}
	h3{
		width: 100%;
		overflow:hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
		margin: 20rpx auto;
	}
	.money{
		// width: 100%;
		height: 80rpx;
		h2{
			font-size: 50rpx;
			// width: 20%;
			color: #ff0000;
			float: left;
		}
		.one{
			// width: 30%;
			line-height: 70rpx;
			float: left;
			margin-left: 20rpx;
			color: #3cff94;
		}
		.two{
			// width: 50%;
			line-height: 70rpx;
			float: right;
			font-size: 25rpx;
		}
	}
}
.body{
	width: 95%;
	margin: 0 auto;
	image{
		width: 100%;
		height: 700rpx;
	}
}
.foot{
	position: fixed;
	bottom: 0;
	width: 100%;
	height: 120rpx;
	background-color: #fff;
	display: flex;
	justify-content: space-between;
	text-align: center;
	color: #fff;
	.left{
		width: 30%;
		height: 80rpx;		
		border-radius: 50rpx;
		// font-size: 40rpx;	
		line-height: 80rpx;
		margin-top: 20rpx;
		margin-left: 20rpx;
		background-color: #1aff66;
	}
	.right{
		width: 60%;
		// height: 80%;
		height: 80rpx;
		border-radius: 50rpx;
		line-height: 80rpx;
		margin-top: 20rpx;
		// padding: 20rpx 10rpx;
		background-color: #ff557f;			
		margin-right: 20rpx;
		.right_right{		
			height: 100%;
			width: 50%;
			float: left;
			border-top-right-radius: 50rpx;
			border-bottom-right-radius: 50rpx;
			background-color: #ff2a2a;
		}
		.right_middle{
			float: left;
			width: 50%;		
			height: 100%;
			border-top-left-radius: 50rpx;
			border-bottom-left-radius: 50rpx;
			background-color: #f5b81c;
		}
	}

}
.u-page {
	padding: 0;
}

.u-cell-icon {
	width: 36rpx;
	height: 36rpx;
	margin-right: 8rpx;
}

.u-cell-group__title__text {
	font-weight: bold;
}
.show2{
	height: 1000rpx;
}

</style>
