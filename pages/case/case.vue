<template>
	<view class="content">
		<view class="head">
			<text>管理</text>
			<image src="../../static/waste.png" mode=""></image>
		</view>
		<view class="body">
			<ul v-for="(item, index) in list" :key="item.id">
				<li>
					<view class="left">
						<!-- @change="checkboxChange" -->
						<u-checkbox-group
							placement="row" 
							iconPlacement="right"
							size='25'
							:key="index"
							:label="item.class"
							:name="item.class"
						>
							<u-checkbox
							>
							</u-checkbox>
							
							<view class="left-right">
								<image :src='item.src' mode=""></image>
							</view>
						</u-checkbox-group>
					</view>	
					<view class="right">
						<text class="title">{{item.class}}</text>
						<view class="body">
								<u-count-down :time="30 * 60 * 60 * 1000" format="HH:mm:ss"></u-count-down>
						</view>
						<view class="foo">
							<text>￥{{item.money1}}</text>
							<!-- @change="valChange" -->
							<u-number-box v-model="value"></u-number-box>
						</view>

					</view>
				</li>
			</ul>
		</view>
		<view class="footer">
			<view class="footer-left">
				<!-- @change="checkboxChange" -->
				<u-checkbox-group
					placement="row" 
					iconPlacement="right"
					size='25'
				>
					<u-checkbox
					shape='circle'>
					</u-checkbox>
					
					<text>全选</text>
				</u-checkbox-group>
			</view>

			<view class="footer-right">
				<text class="title">合计：</text>
				<text class="money">￥{{money}}</text>
				<text style="margin-left: 10rpx;">(<text>{{piece}}</text>件）</text>
			</view>			
		</view>
		<view class="foot">
			<view class="left" @click="cancel">取消</view>
			<view class="right" @click="payment">支付</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// onemoney:20.00,
				money:0,
				piece:0,
				value:'',
				list:[
					{
						id:1,
					    src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fp0.meituan.net%2Fdpdeal%2F56048831dd9c72e95c61d0cf358c0f1d414652.jpg%2540640w_1024h_1e_1l%257Cwatermark%3D1%26%26r%3D1%26p%3D9%26x%3D2%26y%3D2%26relative%3D1%26o%3D20&refer=http%3A%2F%2Fp0.meituan.net&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1658052101&t=fe2bc88957446da13d49fadee41121a9',
					    class: "探病慰问生日鲜花爱情鲜花20枝香槟色玫瑰花",
					    money: "99.9",
						money1:'19.9',
					    go: "去购买"
					},
					{
						id:2,
					    src: 'http://mms2.baidu.com/it/u=3440729924,355188624&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=450&h=450',
					    class: "探病慰问生日鲜花爱情鲜花问候长辈6枝向日葵",
					    money: "99.9",
						money1:'19.9',
					    go: "去购买"
					},
					{
						id:3,
					    src: 'http://mms2.baidu.com/it/u=3707789526,188546141&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=350&h=350',
					    class: "探病慰问生日鲜花爱情鲜花问候长辈3枝向日葵",
					    money: "99.9",
						money1:'19.9',
					    go: "去购买"
					},
					{
						id:4,
					    src: 'http://mms2.baidu.com/it/u=1348139824,2249825676&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=573',
					    class: "探病慰问生日鲜花爱情鲜花问候长辈12枝向日葵",
					    money: "99.9",
						money1:'19.9',
					    go: "去购买"
					},
				]
			}
		},
		methods: {
			// 支付
			payment(){
				uni.navigateTo({
					url:'/pages/payment/payment'
				})
			},
			// 取消
			cancel(){}
		}
	}
</script>

<style lang="scss">
.content{
	height: 100vh;
}
.head{
	width: 100%;
	padding: 30rpx 30rpx;
	font-size: 40rpx;
	// color: red;
	font-weight: 600;
	box-sizing: border-box;
	box-shadow: 0 0 7px #999;
	image{
		width: 5%;
		height: 50rpx;
		float: right;
		vertical-align: middle;
	}
}
.body{
	margin-bottom: 220rpx;
	width: 100%;
	ul{
		margin: 0;
		padding: 0;
		width: 100%;
		list-style: none;
		li{
			width: 100%;
			height: 260rpx;
			padding: 30rpx;
			border: 1rpx solid #ccc;
			border-top: 0;
			box-sizing: border-box;
			.left{
				width: 45%;
				float: left;
				.left-right{
						width: 70%;
						height: 200rpx;
						padding-left: 30rpx;
					image{
						width: 100%;
						height: 100%;
					}
				}

			}
			.right{
				float: left;
				width: 55%;
				height: 200rpx;
				white-space: nowrap;
				text-overflow: ellipsis;				
				overflow: hidden;
				.title{
					width: 100%;
					font-size: 35rpx;
				}
				.body{
					width: 100%;
					margin: 15rpx 0 0 60%;
					margin-bottom: 0;
				}
				.foo{
					width: 100%;
					display: flex;
					// height: 40rpx;
					// height: 50rpx;
					margin-top: 30rpx;
					justify-content: space-between;
					z-index: 10;
					text{
						font-size: 40rpx;
						color: red;
					}
				}
			}
		}
	}
}
.footer{
	position: fixed;
	bottom: 110rpx;
	width: 100%;
	height: 100rpx;
	line-height: 90rpx;
	background-color: #fff;
	padding-left: 30rpx;
	z-index: 100 !important;
	.footer-left{
		float: left;
		width: 60%;
		text{
			font-size: 40rpx;
			margin-left: 10rpx;
			font-weight: 600;
		}
	}
	.footer-right{
		float: left;
		font-size: 35rpx;
		.money{
			color: red;
		}
	}
}
.foot{
	position: fixed;
	bottom: -1rpx;
	width: 100%;
	height: 120rpx;
	background-color: #fff;
	display: flex;
	justify-content: space-around;
	text-align: center;
	color: #fff;
	z-index: 100 !important;
	.left{
		width: 40%;
		height: 80rpx;		
		border-radius: 50rpx;
		float: right;
		line-height: 80rpx;
		margin-top: 20rpx;
		background-color: #ccc;
	}
	.right{
		width: 40%;
		height: 80rpx;		
		border-radius: 50rpx;
		float: right;
		line-height: 80rpx;
		margin-top: 20rpx;
		background-color: red;
	}
}
</style>
