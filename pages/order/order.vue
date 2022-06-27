<template>
	<view class="content">
		<u-tabs :list='list1' @click="click"></u-tabs>
		<ul class='box' v-show="acId==1"  v-for="item in list2" :key="item.id">
			<li>
				<view class="up">
					<view class="left">
						<image :src='item.src'></image>
					</view>
					<view class="right">
						<view class="title">
							{{item.class}}
						</view>
						<view class="small_title">
							<text>向日葵 12枝</text>
							<text>X1</text>
						</view>
						<view class="bottom">
							<text class="span1">含运费险服务 </text>
							<text> 实付款￥{{item.money1}}</text>
						</view>
					</view>
				</view>
				<view class="down">
					<ul>
						<li class="one">更多</li>
						<li class="two">延长收货</li>
						<li class="three">查看物流</li>
						<li class="four">确认收货</li>
					</ul>
				</view>
			</li>
			<li>
				<view class="up">
					<view class="left">
						<image :src='item.src'></image>
					</view>
					<view class="right">
						<view class="title">
							{{item.class}}
						</view>
						<view class="small_title">
							<text>向日葵 12枝</text>
							<text>X1</text>
						</view>
						<view class="bottom">
							<text class="span1">含运费险服务 </text>
							<text> 实付款￥{{item.money1}}</text>
						</view>
					</view>
				</view>
				<view class="down">
					<ul>
						<li class="one">更多</li>
						<li class="two">延长收货</li>
						<li class="three">查看物流</li>
						<li class="four">评价</li>
					</ul>
				</view>
			</li>
			
			<li>
				<view class="up">
					<view class="left">
						<image :src='item.src'></image>
					</view>
					<view class="right">
						<view class="title">
							{{item.class}}
						</view>
						<view class="small_title">
							<text>向日葵 12枝</text>
							<text>X1</text>
						</view>
						<view class="bottom">
							<text class="span1">含运费险服务 </text>
							<text> 实付款￥{{item.money1}}</text>
						</view>
					</view>
				</view>
				<view class="down">
					<ul>
						<li class="one">更多</li>
						<li class="two">再来一单</li>
						<li class="three">追加评论</li>
						<li class="three">查看物流</li>
					</ul>
				</view>
			</li>
		</ul>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				acId:1,
				list1: [
					{
					// id:1,
					name: '全部',
				}, {
					// id:2,
					name: '待付款',
				}, {
					// id:3,
					name: '待发货'
				}, {
					// id:4,
					name: '待收货'
				}, {
					// id:5,
					name: '待评价'
				},{
					// id:6,
					name:'售后'
				}],
				list2:[{
					id:1,
					src: 'http://mms2.baidu.com/it/u=3290724860,3578281849&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=500',
					class: "探病慰问生日鲜花爱情鲜花问候长辈12枝向日葵",
					money: "99.9",
					money1: "59.9",
					people:"134",
				}
				]
			}
		},
		methods: {
			click(item) {
				console.log('item', item);
			}
		}
	}
</script>

<style lang="scss">
.content{
	margin: 0;
	padding: 0;
	background-color: #ECF0F2;
	height: 100%;
	.active{
		background-color: #f3ad9f;
	}
	.box{	
		margin: 0;
		padding: 0;
		list-style: none;
		width: 95%;
		margin: 0 auto;
		li{
			width: 100%;
			height: 480rpx;
			box-sizing: border-box;
			padding: 30rpx;
			padding-top: 70rpx;
			background-color: #fff;
			border-radius: 40rpx;
			margin: 20rpx 0 30rpx 0;
			.up{
				width: 100%;
				display: flex;
				// background-color: aquamarine;
				justify-content: space-between;
				.left{
					width: 33%;
					height: 250rpx;
					image{
						width: 100%;
						height: 100%;
					}
				}
				.right{
					position: relative;
					width: 60%;
					height: 250rpx;
					.title{
						width: 100%;
						overflow: hidden;
						text-overflow: ellipsis;
						white-space: nowrap;
					}
					.small_title{
						margin-top: 10rpx;
						display: flex;
						color: #999;
						justify-content: space-between;
					}
					.bottom{
						position: absolute;
						bottom: 0;
						.span1{
							color: #999;
							margin-right: 5rpx;
						}
					}
				}
			}
			.down{
				width: 100%;
				height: 140rpx;
				position: relative;
				// background-color: #beeeff;
				ul{
					margin: 0;
					padding: 0;
					width: 100%;
					display: flex;
					// height: 100rpx;
					// line-height: 100rpx;
					// background-color: aqua;
					justify-content: space-between;
					list-style: none;
					position: absolute;
					bottom: 0;
					li{
						padding-top: 0;
						width: 25%;
						height: 70rpx;
						text-align: center;
						// padding: 20rpx 0;
						line-height: 70rpx;
						box-sizing: border-box;
						// background-color: #beeeff;
						font-size: 20rpx;

					}
					.one{
						text-align: left;
						width: 18%;
						color: #999;
					}
					.two{
						border: 1rpx solid #ccc;
					}
					.three{
						border: 1rpx solid #ccc;
					}
					.four{
						border: 1rpx solid #ff9122;
						color: #ff9122;
					}
				}
			}
		}

	}
}

</style>
