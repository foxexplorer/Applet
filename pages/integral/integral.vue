<template>
	<view class="content">
		<view class="head">
			<view class="left">
				<view class="top">我的积分</view>
				<view class="bottom">20335</view>
			</view>
			<view class="right">
				<ul>
					<li>
						<image src="../../static/商品 (2).png" mode=""></image>
						<view class="">
							全部商品
						</view>
					</li>
					<li>
						<image src="../../static/积分.png" mode=""></image>
						<view class="">
							全部商品
						</view>
					</li>
					<li>
						<image src="../../static/笔记，记录.png" mode=""></image>
						<view class="">
							全部商品
						</view>
					</li>
				</ul>
			</view>
		</view>
		<view class="body">
			<h3>积分任务</h3>
			<ul>
				<li class='li-one'>
					<view class="one">
						<image src="../../static/签到 (1).png" mode=""></image>
					</view>
					<view class="two">
						<view class="top">
							每日签到
						</view>
						<view class="bottom">
							每天签到可得2~10个积分
						</view>
					</view>
					<view class="three">
						<view class="three_body">
							去签到
						</view>
					</view>
				</li>
				<li class='li-two'>
					<view class="one" style="background-color: #1aafcc;">
						<image src="../../static/商品 (2).png" mode=""></image>
					</view>
					<view class="two">
						<view class="top">
							购物消费
						</view>
						<view class="bottom">
							您的每笔消费订单都可以得到积分
						</view>
					</view>
					<view class="three">
						<view class="three_body">
							去购物
						</view>
					</view>
				</li>
				<li  class='li-three'>
					<view class="one" style="background-color: #cc5109;">
						<image src="../../static/充值.png" mode=""></image>
					</view>
					<view class="two">
						<view class="top">
							充值得积分
						</view>
						<view class="bottom">
							您的每笔充值订单都可以得到积分
						</view>
					</view>
					<view class="three">
						<view class="three_body">
							去充值
						</view>
					</view>
				</li>
			</ul>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
.content{
	width: 100%;
	background-color: #ECF0F2;
}
.head{
	padding-top: 60rpx;
	width: 100%;
	height: 350rpx;
	color: #fff;
	background-color: #ffb5a6;
	display: flex;
	// justify-content: ;
	.left{
		width: 40%;
		height: 200rpx;
		padding-left: 30rpx;
		// background-color: #fff;
		.top{
			font-size: 40rpx;
		}
		.bottom{
			font-size: 80rpx
		}
	}
	.right{
		width: 60%;
		height: 200rpx;
		ul{
			width: 100%;
			height: 200rpx;
			list-style: none;
			margin: 0;
			padding: 0;
			display: flex;
			// line-height: 100rpx;
			justify-content: space-between;
			li{
				padding-top: 20rpx;
				width: 33.3%;
				height: 100%;
				text-align: center;
				image{
					width: 50%;
					height: 70rpx;
				}
			}
		}
	}
}
.body{
	width: 100%;
	height: 500rpx;
	margin: -140rpx auto;
	margin-bottom: 0;
	padding: 30rpx 0;
	border-top-left-radius: 40rpx;
	border-top-right-radius: 40rpx;
	background-color: #fff;
	h3{
		width: 100%;
		height: 50rpx;
		padding-left: 40rpx;
		padding-bottom: 30rpx;
	}
	ul{
		margin: 0;
		padding: 0;
		list-style: none;
		li{
			width: 85%;
			height: 200rpx;
			margin: 0 auto;	
			padding: 35rpx 0 0 20rpx;
			box-sizing: border-box;// 
			// line-height: 150rpx;
			display: flex;
			border-bottom: 1rpx solid #ccc;
			justify-content: space-between;

			.one{
				width: 20%;
				height: 120rpx;
				background-color: #ffa526;
				border-radius: 50%;
				display: flex;
				justify-content: center;

				image{
					margin-top: 20rpx;
					width: 60%;
					height: 75rpx;
				}
			}
			.two{
				width: 50%;
				height: 100%;
				padding-left: 15rpx;
				.top{
					font-size: 40rpx;
				}
				.bottom{
					margin-top: 10rpx;
					font-size: 20rpx
				}
			}
			.three{
				width: 26%;
				height: 100%;
				text-align: center;
				.three_body{
					background-color: red;
					height: 70rpx;
					margin-top: 20rpx;
					line-height: 70rpx;
					border-radius: 40rpx;
					color: #fff;
				}
			}

		}
	}
}
</style>
