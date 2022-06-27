<template>
	<view class="content">
		
		<!-- 搜索 -->
		<view class="box">
			<u-search height = '70rpx' :showAction = "false" placeholder="请输入内容" bgColor='#fff'></u-search>
		</view>
		
		<!-- 轮播图 -->
		<view class="swiper_box">
			<u-swiper
				:list="list1"
				height='220'
				:circular = "true"
				:indicator = 'true'
			>
			</u-swiper>
		</view>
		
		<!-- 分类 -->
		<view class="Navigation">
			    <u-scroll-list>
			        <view v-for="(item, index) in Nav" :key="item.id" class="Nav">
						<view class="Nav-one">
							<image :src="item.src"></image>
						</view>
						<view class="Nav-two">
							<text>{{item.name}}</text>
						</view>
			        </view>
			    </u-scroll-list>
		</view>
		
		<!-- 优惠券 -->
		<view class="nav_box">
				<image  :src="require('../../images/2.png')" alt=""></image>
				<image :src="require('../../images/3.png')" alt=""></image>
		</view>
		<!-- 分割 -->
		<u-notice-bar :text="text1" color="#ad5700" bgColor="#ffd0d0"></u-notice-bar>
		<!-- 下部分内容 -->
		<view class="list_box">
			<view class="titbar clearfix">
				<h2>部分商品</h2>
				<view class="more">
					<text @click='but'>更多商品</text><image :src="require('../../images/hsj.png')">
				</view>
				
			</view>
			<view class="list2" v-show="acId==1">
				<view id="demo1" class="scroll-view-item clearfix one" style="background-color: #ffc499;" v-for="(item,index) in list2" :key="index">
					<ul>
						<li>
							<view class="pic-box">
								<image :src="item.src" alt="">
							</view>
							<view class="txt-box">
								<P class="left">
									<p class='span1'>{{item.class}}</p>
									<p class="span2">{{item.time}}</p>
								</P>
								<p class="right">
									<text class="btn" @click='btn'>{{item.money}}</text>
								</p>
							</view>
						</li>
					</ul>
				</view>
				<view class="footer">
					没有内容了
				</view>
			</view>
		</view>
		<view class="popup">
			<u-popup :show="show" @close="close" mode='center' bgColor='transparent'>
				<view>
					<image src="../../static/logo.png"></image>
					<view style="text-align: center;color: #fff;font-size: 40rpx;">
						欢迎来到<text style="color: #ffc499;">罗曼蒂克</text>花坊
					</view>
				</view>
			</u-popup>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:true,
				scrollTop:0,
				acId:'1',
				flag:false,
				text1:'现在抢购还送一束满天星！！',
				Nav:[
					{
						id:1,
						src:'../../static/knx.png',
						name:'康乃馨'
					},
					{
						id:2,
						src:'../../static/yjx.png',
						name:'郁金香'
					},
					{
						id:3,
						src:'../../static/bh.png',
						name:'百合'
					},
					{
						id:4,
						src:'../../static/mg.png',
						name:'玫瑰'
					},
					{
						id:5,
						src:'../../static/xrk.png',
						name:'向日葵'
					},
					{
						id:6,
						src:'../../static/hl.png',
						name:'花篮'
					},
					{
						id:7,
						src:'../../static/sp.png',
						name:'双拼'
					}
				],
				list1: [
					'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.zcool.cn%2Fcommunity%2F01c3305b35cc31a80120b959f9d828.jpg%402o.jpg&refer=http%3A%2F%2Fimg.zcool.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657853452&t=8b3a4a55611790942b4f6df0bec639c7',
					
					'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.zcool.cn%2Fcommunity%2F0124995df0f5c3a801219ccebc1c94.jpg%402o.jpg&refer=http%3A%2F%2Fimg.zcool.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657853452&t=0b9008ed28d701be2aac64477a7e38ba',
					// https://img.zcool.cn/community/016fea5aa5ca8fa801206d961b092c.jpg@1280w_1l_2o_100sh.jpg
					'../../static/banner3.jpg',
					
					'https://img.zcool.cn/community/0136195ad40f73a8012040296b9439.jpg@1280w_1l_2o_100sh.jpg'
	            ],
				list:[
					{
						id:1,
						name:'优惠券',
					},
					{
						id:2,
						name:'合作品牌',
					},
					{
						id:3,
						name:'风格测试',
					}
				],
				list2:[
					{	
				        src: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg10.360buyimg.com%2Fimgzone%2Fjfs%2Ft1%2F163731%2F23%2F7062%2F268623%2F602f8abdE098e5991%2Ff8102e5668bf1f67.jpg&refer=http%3A%2F%2Fimg10.360buyimg.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657855188&t=ce0652d4654382a0911b5c4f6ee4ea0d",
				        class: "探病慰问生日鲜花问候长辈12枝郁金香",
				        time: "99.9",
				        money: "去购买"
				    },
				    {
				        src: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.alicdn.com%2Fimgextra%2Fi2%2F713401482%2FO1CN01QPYl8q1MonZV9q1DO_%21%21713401482.jpg&refer=http%3A%2F%2Fimg.alicdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657855188&t=83c39c2554f544b06772f04d983d9517",
				        class: "探病慰问生日鲜花问候长辈6枝郁金香",
				        time: "99.9",
				        money: "去购买"
				    },
				    {
				        src: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg11.360buyimg.com%2Fimgzone%2Fjfs%2Ft1%2F165312%2F3%2F6886%2F305483%2F602f8abaEdc91ddbf%2F3a6a308b7a9f379e.jpg&refer=http%3A%2F%2Fimg11.360buyimg.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657855188&t=5f54afd798586230a9e27f6dd9d1d347",
				        class: "探病慰问生日鲜花问候长辈6枝郁金香",
				        time: "99.9",
				        money: "去购买"
				    },
				    {
				        src: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.alicdn.com%2Fi3%2F537980673%2FO1CN01kIqtUe1GqHE8NxRdB_%21%21537980673.jpg&refer=http%3A%2F%2Fimg.alicdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657855188&t=133a5944afd0742278db137ecf75164d",
				        class: "探病慰问生日鲜花问候长辈16枝郁金香",
				        time: "99.9",
				        money: "去购买"
				    },
				    {
				        src: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.alicdn.com%2Fi3%2F2207538310170%2FO1CN01Qz1Fue1D7tv7wV0r7_%21%212207538310170.jpg&refer=http%3A%2F%2Fimg.alicdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657855188&t=b1f7a55fd12fbc71aaed467b0d4dd340",
				        class: "探病慰问生日鲜花问候长辈8枝郁金香",
				        time: "99.9",
				        money: "去购买"
				    },
				    {
				        src: "http://t14.baidu.com/it/u=600254218,3889376200&fm=224&app=112&f=JPEG?w=500&h=500",
				        class: "探病慰问生日鲜花问候长辈20枝郁金香",
				        time: "99.9",
				        money: "去购买"
				    },
				    {
				        src: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.alicdn.com%2Fi3%2F1744362897%2FO1CN01IxyyhN1XGs1alxJiD_%21%211744362897-0-lubanu-s.jpg&refer=http%3A%2F%2Fimg.alicdn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657855188&t=d1ef1a0ba6e3ba6ba80a06f10e964eb0",
				        class: "探病慰问生日鲜花爱情鲜花问候长辈鲜花双拼",
				        time: "99.9",
				        money: "去购买"
				    },
				    {
				        src: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fci.xiaohongshu.com%2F79f2a0a5-0fef-6075-be68-48ab19a945e8%3FimageView2%2F2%2Fw%2F1080%2Fformat%2Fjpg&refer=http%3A%2F%2Fci.xiaohongshu.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657855310&t=e6385f0307605ab5a2107ce62c339545",
				        class: "探病慰问生日鲜花爱情鲜花问候长辈鲜花双拼",
				        time: "99.9",
				        money: "去购买"
				    },
				   
				]
			}
		},
		onLoad() {

		},
		methods: {
			Taggie(id){
				this.acId = id
			},
			btn(){
				uni.navigateTo({
					url:"/pages/goods/goods"
				})
			},
			but(){
				uni.switchTab({
					url:"../list/list"
				})
			},
			close() {
			  this.show = false
			  // console.log('close');
			},
		}
	}
</script>

<style lang="scss">
	.content {
		background-color: #ECF0F2;
		padding-top: calc(var(-–window-bottom)+20rpx);
	}
	.box{
		width: 100%;
		height: 120rpx;
		// background-color: #ffb5a6;
		border-bottom-left-radius: 30%;
		border-bottom-right-radius: 30%;
		padding: 10rpx;
		box-sizing: border-box;
	}
	.swiper_box{
		width: 100%;
		height:450rpx;
		margin: 0 auto;
		overflow: hidden;
		u-swiper{
			// width: 100%;
			// height: 100%;
		}
	}
	.nav_box{
		display: flex;
		justify-content: space-between;
		width: 94%;
		height: 230rpx;
		margin: 0 auto;
		padding: 10rpx;
		box-sizing: border-box;
		
		image{	
	    width: 50%;
	    height: 100%;
	    float: left;
	    cursor: pointer;
		}	
	}
	.Navigation{
		width: 95%;
		height: 300rpx;
		margin: 20rpx auto;
		margin-bottom: 0;
			.Nav{
				.Nav-one{
					width: 150rpx;
					height: 150rpx;
					background-color: #fff;
					border-radius: 50%;
					margin: 0 auto;
					margin-top: 25rpx;
					// text-align: center;
					margin-right: 40rpx;
					text-align: center;
					image{
						margin-top: 25rpx;
						width: 100rpx;
						height: 100rpx;
					}
				}
				.Nav-two{
					width: 150rpx;
					text-align: center;
					padding-top: 10rpx;
					color: #6b6b6b;
				}
			}
		}
	
	.list_box{
		width: 100%;
		// height: 300rpx;
		padding-top:20rpx;
		margin-top: 40rpx;
		box-sizing: border-box;
		// padding-bottom: 50rpx;
		background-color: #fff;
		.titbar{
			width: 95%;
			margin: 0 auto;
			h2{
				display: inline-block;
			}
			.more{
				float: right;
				// text-decoration: none;
				color: #83a4ad;
				image{
					width: 20rpx;
					height: 20rpx;
				}
			}

		}
		
		.list2{
			width: 98%;
			// height:100%;
			margin: 30rpx auto;
			margin-bottom: 0rpx;
			padding-bottom: 30rpx;
			.footer{
				width: 100%;
				text-align: center;
			}
			.scroll-view-item {
				width: 100%;
				ul{
					width: 100%;
					margin: 0;
					padding: 0;	
					li{
						float: left;
						padding-top: 40rpx;
					    background-color: #fff;
					    width: 47.5%;
					    height: 500rpx;
					    cursor: pointer;
						list-style: none;
						padding: 0 8rpx;
						.pic-box{
							// position: relative;
							width: 100%;
							height: 300rpx;
							image{
							width: 100%;
							height: 100%;
							// margin-bottom: 10px;
							border-radius: 5%;
							}
						}
						.txt-box{
							padding: 10px 10px;
							width: 100%;
							// height: 100%;
							font-size: 30rpx;
							.left{
								width: 90%;
								// float: left;
								// margin-left: 10rpx;
								.span1{
									width: 100%;
									overflow:hidden;
									text-overflow: ellipsis;
									white-space: nowrap;
								}
								.span2{
								color: red;
								}
							}
							.right{
								height: 75rpx;
								line-height: 75rpx;
								width: 50%;
								// float: left;
								
								.btn{
									padding: 5rpx 15rpx;
									background-color: #80c4ae;
									border-radius: 4px;
									line-height: 30px;
									color: #fff;
									margin-top: 10rpx;
									text-align: center;
									text-decoration: none;
								} 
							}
						}
					}
				}
			}
		}
	}
	
</style>
