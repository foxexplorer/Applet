<template>
	<view class="content">
		<!--  -->
		<view class="header">
			<view class="head_left">
				<view class="left-image">
					<image :src="require('../../images/head.jpg')" mode=""></image>
				</view>
				<view class="left-text">
					<text class='text1'>小阳光</text><br>
					<text class='text2'>13445645456</text>
				</view>
			</view>
			<view class="head_right">
				<view class="right-text">
					<image src="../../static/Sign.png" mode=""></image>
					<text>签到</text>
				</view>
			</view>
		</view>
		
		<!--  -->
		<view class="list">
			<ul v-for="item in list" :key='item.id'>
				<li>
					<text>{{item.title}}</text><br>
					<text>{{item.name}}</text>
				</li>
			</ul>
			<view class="member">
				<view class="member-left">
					<text class="left-text1">优享会员卡 |</text>
					<text class="left-text2">{{text}}</text>
				</view>
				<view class="member-right">
					<text>
						会员中心
					</text>
				</view>
			</view>
		</view>

		<!--  -->

		<view class="we_box">
			<view class="title">
				我的活动
			</view>
			<ul v-for="item in list2" :key="item.id">
				<li>
					<!-- <view class="up"> -->
						<image :src="item.src" mode=""></image>
					<!-- </view> -->
					<view class="down">
						{{item.title}}
					</view>
				</li>
			</ul>
		</view>
		
		<view class="we_box we2_box">
			<view class="title">
				我的服务
			</view>
			<ul>
				<li @click='follow'>
					<image src="/static/follow.png" mode=""></image>
					<view class="down">
						我的关注
					</view>
				</li>
				<li @click='integral'>
					<image src="/static/integral.png" mode=""></image>
					<view class="down">
						积分商城
					</view>
				</li>
				<li @click="order">
					<image src="/static/order.png" mode=""></image>
					<view class="down">
						我的订单
					</view>
				</li>
				<li @click='address'>
					<image src="/static/address.png" mode=""></image>
					<view class="down">
						地址管理
					</view>
				</li>
				<li>
					<image src="/static/service.png" mode=""></image>
					<view class="down">
						客服与帮助
					</view>
				</li>
				<li @click="opinion">
					<image src="/static/opinion.png" mode=""></image>
					<view class="down">
						意见反馈
					</view>
				</li>
			</ul>
		</view>
		
		<u-popup :show="show"
		mode="bottom"  
		@close="close" 
		:closeable='true' closeIconPos='top-right'>
			<view class="show">
				<text>意见反馈</text>
				<view  class="show_content">
					<u--textarea placeholder="请输入内容" confirmType='done'></u--textarea>
				</view>
			</view>
		</u-popup>
		
		<!--  -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:false,
				text:'2023-12-31到期',
				list:[
					{
						id:1,
						title:"200",
						name:'余额',
					},
					{
						id:2,
						title:"2",
						name:'红包',
					},
					{
						id:3,
						title:"2",
						name:'优惠券',
					},
					{
						id:4,
						title:"2000",
						name:'积分',
					}
				],
				list2:[
					{
						id:1,
						src:'/static/hot.png',
						title:"抢购"
					},
					{
						id:2,
						src:'/static/Spell.png',
						title:"拼团"
					},
					{
						id:3,
						src:'/static/Bargain.png',
						title:"砍价"
					}
				],
				list3:[
					{
						id:1,
						src:'/static/follow.png',
						title:"我的关注"
					},
					{
						id:2,
						src:'/static/integral.png',
						title:"积分商城"
					},
					{
						id:3,
						src:'/static/order.png',
						title:"我的订单"
					},
					{
						id:4,
						src:'/static/address.png',
						title:"地址管理"
					},
					{
						id:5,
						src:'/static/service.png',
						title:"客服与帮助"
					},
					{
						id:6,
						src:'/static/opinion.png',
						title:"意见反馈"
					},
				]
			}
		},
		methods: {
			follow(){
				uni.navigateTo({
					url:"/pages/follow/follow"
				})
			},
			integral(){
				uni.navigateTo({
					url:"/pages/integral/integral"
				})
			},
			address(){
				uni.navigateTo({
					url:'/pages/address/address'
				})
			},
			order(){
				uni.navigateTo({
					url:"/pages/order/order"
				})
			},
			opinion(){
				// uni.navigateTo({
				// 	url:"/pages/payment/payment"
				// })
				this.show = true
			},
			close() {
			  this.show = false
			},
		}
	}
</script>

<style lang="scss">
	.content{
		width: 100%;
		height: 100vh;
		background-color: #ECF0F2;
		// padding-bottom: calc(var(-–window-bottom)+20rpx);
		// padding-top: calc(var(-–window-bottom)+10rpx);
	}
	// 
	.header{
		width: 100%;
		height: 250rpx;
		background-color: #ffb5a6;
		// line-height: 300rpx;
		.head_left{
			// padding: 60rpx 0 0 20rpx;
			margin: 60rpx 0 0 30rpx;
			width: 60%;
			height: 60%;
			overflow: hidden;
			float: left;
			.left-image{
				width: 35%;
				height: 100%;
				float: left;
				image{
					width: 100%;
					height: 100%;
					border-radius: 50%;
					// vertical-align: middle;
				}
			}
			.left-text{
				margin: 30rpx 0 0 20rpx;
				float: left;
				line-height: 50rpx;
				.text1{
					font-weight: 600;
					font-size: 35rpx;
				}
			}
		}
		.head_right{
			width: 26%;
			height: 15%;
			background-color: #fff;
			float: left;
			margin: 110rpx 0 0 0;
			padding: 10rpx 5rpx;
			border-radius: 40rpx;
			.right-text{
				width: 100%;
				height: 100%;
				display: flex;
				justify-content: center;
				// background-color: #30d9ff;
				image{
					width: 20%;
					height: 100%;
					// padding-left: 20rpx;
					
				}
				text{
					font-size: 33rpx;
					padding-left: 20rpx;
					font-weight: 600;
				}
			}
		}
	}
	
	// 
	.list{
		position: relative;
		width: 100%;
		height: 260rpx;
		background-color: #ffb5a6;
		color: #fff;
		ul{
			margin: 0;
			padding: 0;
			width: 100%;
			// display: flex;
			// justify-content: space-between;
			// height: 200rpx;
			list-style: none;
			li{
				width: 25%;
				text-align: center;
				float: left;
				font-size: 40rpx
			}
		}
		.member{
			// color: #f8ff6e;
			position: absolute;
			bottom: 0rpx;
			left: 20rpx;
			// padding-top: -200rpx;
			width: 95%;
			height: 120rpx;
			margin: 0 auto;
			margin-bottom: 0;
			display: flex;
			justify-content: space-between;
			line-height: 120rpx;
			border-top-left-radius: 40rpx;
			border-top-right-radius: 40rpx;
			background-color: #383838;
			.member-left{
				width: 70%;
				border-top-left-radius: 40rpx;
				text-align: center;
				display: flex;
				justify-content: space-around;
				background-image:-webkit-linear-gradient(top,#fff,#f8ff6e);
				-webkit-background-clip:text;
				-webkit-text-fill-color:transparent;
				// background-color: #fff;
				.left-text1{
					font-size: 40rpx
				}
				.left-text2{
					font-size: 30rpx
				}
			}
			.member-right{
				width: 30%;
				border-top-right-radius: 40rpx;
				// background-color: #ffb5a6;
				text-align: center;
				text{
					width: 70%;
					height: 90%;
					padding: 10rpx 25rpx;
					background-color: #fff6ab;
					color: #000;
					font-weight: 600;
					border-radius: 40rpx;
				}
			}
		}
	}
	

	// 
	.we_box{
		width: 100%;
		height: 300rpx;
		background-color: #fff;

		.title{
			width: 95%;
			margin: 0 auto;
			// background-color: #fff;
			font-size: 40rpx;
			font-weight: 600;
			padding: 35rpx 0;
		}
		ul{
			width: 90%;
			margin: 0;
			padding: 0;
			list-style: none;
			margin: 0 auto;
			// display: flex;	
			// justify-content: space-between;	
			background-color: #30d9ff;
			li{
				width: 33%;
				float: left;
				text-align: center;
				image{
					width: 75rpx;
					height: 80rpx;
				}
				// float: left;
			}
		}
	}
	
	// 
	.we2_box{
		margin-top: 30rpx;
		height: 500rpx;
		ul{
			li{
				margin-bottom: 50rpx;
			}
		}
	}
	// 
	.show{
		padding: 20rpx 20rpx;
		height: 280rpx;
		text{
			font-size: 40rpx;
		}
		.show_content{
			margin: 30rpx auto;
			margin-bottom: 0;
			width: 95%;
		}
	}
</style>
