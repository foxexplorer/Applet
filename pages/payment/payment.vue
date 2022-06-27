<template>
	<view class="content">
		<view class="ress">
			<!-- <h3>收货地址</h3> -->
			<view class="head">
				收货地址：
			</view>
			<view class="have">
				<view class='have_one'>张三</view>
				<view class='have_two'>xxxxxxxxxx</view>
			</view>
		</view>
		<view class="box">
			<view class="head_box">
				<view class="head_left">
					<image :src="list.src"></image>
				</view>
				<view class="head_right">
					<h3>{{list.class}}</h3>
					<view class="body">
						<text class="one">￥{{list.money1}}</text>
						<text class="two">X{{list.num}}</text>
					</view>				
					<view class="bottom">
						<text class="one">取消支付</text>
						<text class="two">找相似</text>
					</view>
				</view>
			</view>
		</view>

		<view class="body_box">
			<view class="body_box1">
				<text class='left'>待支付：</text><text class='right'>￥{{list.money1}}</text>
			</view>
			<view class="body_box2">
				<u-count-down :time="30 * 60 * 60 * 1000" format="HH:mm:ss"></u-count-down>
			</view>
		</view>

		<view class="list">
			<ul>
				<li>
					<u-radio-group
					    v-model="radiovalue1"
					    placement="column"
					  >
					  <!-- @change="groupChange" -->
					    <u-radio
					      :customStyle="{marginBottom: '30px'}"
						  labelSize='20px'
					      v-for="(item, index) in radiolist1"
					      :key="index"
					      :label="item.name"
					      :name="item.name"
					    >
						<!-- @change="radioChange" -->
						
					    </u-radio>
					  </u-radio-group>
				</li>
			</ul>
		</view>
		<view class="foot">
			<view class="middle" @click="order">支付</view>
		</view>
		<u-modal :show="show"
		 ref="uModal"
		 :closeOnClickOverlay='true'
		 :showConfirmButton='false'
		  :asyncClose="true"
		  width='350rpx'
		  @close='close'>支付成功</u-modal>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:false,
				list:
					{
						src: 'http://mms2.baidu.com/it/u=3290724860,3578281849&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=500',
					    class: "探病慰问生日鲜花爱情鲜花问候长辈12枝向日葵",
					    money1: "59.9",
						num:1,
					},
				  radiolist1: [{
					name: '微信支付',
					disabled: false
				  },
					{
					  name: '支付宝支付',
					  disabled: false
					},
					{
					  name: '绑卡支付',
					  disabled: false
					}
				  ],
				  radiovalue1: '微信支付',
				}
			// }
		},
		methods: {
			// 
			order(){
				this.show = !this.show
			},
			close() {
			  this.show = false
			  uni.navigateTo({
			  	url:'/pages/order/order'
			  })
			},
		}
	}
</script>

<style lang="scss">
	.content{
		margin: 0;
		padding: 0;
		background-color: #ECF0F2;
			}
	.ress{
		width: 100%;
		margin: 0 auto;
		.head{
			width: 100%;
			padding: 20rpx;
			background-color: #fff;
		}
		.have{
			width: 100%;
			height: 150rpx;
			display: flex;
			line-height: 150rpx;
			background-color: #fff;
			// text-align: center;
			.have_one{
				width: 25%;
				height: 100%;
				font-weight: 600;
				font-size: 35rpx;
				text-align: center;
				border: 1rpx solid #ccc;
				border-right: 0;
			}
			.have_two{
				width: 75%;
				height: 100%;
				font-size: 30rpx;
				padding-left:20rpx;
				border: 1rpx solid #ccc;
				box-sizing: border-box;
			}
		}
	
	}
	
	.box{
		width: 100%;
		background-color: #fff;
		height: 380rpx;
		margin-top: 20rpx;
		padding-top: 5rpx;
		.head_box{
			width: 90%;
			height: 300rpx;
			margin: 15rpx auto;
			display: flex;
			justify-content: space-between;
			// border: 1rpx solid #ccc;
			padding: 20rpx;
			.head_left{
				width: 40%;
				height: 300rpx;
				background-color: #fff;
				image{
					width: 100%;
					height: 100%;
				}
			}
			.head_right{
				width: 57%;
				height: 300rpx;
				// background-color: aqua;
				h3{
					width: 100%;
					height: 70rpx;
					overflow:hidden;
					text-overflow: ellipsis;
					white-space: nowrap;
				}
				.body{
					display: flex;
					height: 70rpx;
					line-height: 70rpx;
					justify-content: space-between;
					.one{
						font-size: 50rpx;
						color: red;
						font-weight: 600;
					}
					.two{
						color: #ccc;
					}
				}
				.bottom{
					display: flex;
					height: 80rpx;
					line-height: 70rpx;
					text-align: center;
					margin-top: 50rpx;
					justify-content: space-between;
					.one{
						border: 1rpx solid #ccc;
						width: 45%;
						height: 100%;
						border-radius: 40rpx;
						color: #ccc;
						// padding: 10rpx 10rpx;
					}
					.two{
						border: 1rpx solid #ccc;
						width: 45%;
						height: 100%;
						border-radius: 40rpx;
						color: #ccc;
						// color: #ccc;
					}
				}
			}
		}
		
	}

	.body_box{
		width: 100%;
		margin: 20rpx auto;
		height: 100rpx;
		// text-align: center;
		display: flex;
		justify-content: space-around;
		line-height: 100rpx;
		font-size: 50rpx;			
		font-weight: 600;
		background-color: #fff;
		.body_box1{
			height: 100rpx;		
			.right{
			color: red;
			}
		}
		.body_box2{
			// height: 100rpx;		
			margin-top: 30rpx;
		}

	}

	.list{
		width: 100%;
		margin: 0 auto;
		background-color: #fff;
		// text-align: center;
		ul{
			margin: 0;
			padding: 40rpx;
			list-style: none;
			li{
				u-radio-group{
					margin-top: 30rpx;
				}
			}
		}
	}
	.foot{
		position: fixed;
		bottom: 0;
		width: 100%;
		height: 120rpx;
		background-color: #fff;
		display: flex;
		justify-content: center;
		text-align: center;
		color: #fff;
		.middle{
			width: 80%;
			height: 80rpx;		
			border-radius: 50rpx;
			// font-size: 40rpx;	
			line-height: 80rpx;
			margin-top: 20rpx;
			margin-left: 20rpx;
			background-color: red;
		}
	}
</style>
