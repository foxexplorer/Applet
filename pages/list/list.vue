<template>
	<view class="content">
		<!-- 搜索 -->
		<view class="box">
			<u-search height = '70rpx' :showAction = "false" placeholder="请输入内容" ></u-search>
		</view>
		
		<!-- 介绍 -->
		<view class="nav_box">
			<view class="n_left">
					<image src="../../static/logo.png"></image>
			</view>
			<view class="n_right">
				<text>陌上花开，</text>
				<text>可缓缓归矣</text>
			</view>
		</view>
		
		<!-- 导航 -->
		<view class="switch_box">
			<view class="box_title">
				<view class="min_box" @click="Taggie(item.id)" :class="{'active':acId==item.id}" v-for="item in list" :key='item.id' >
					
					{{item.name}}
				</view>
			</view>
		</view>
		<!-- 分类 -->
		<view class="classify">
			<ul class='title'>
				<li class='li-one'>种类</li>
				<li class='li-one'>枝数</li>
				<li class='li-one'>颜色</li>
			</ul>
			<ul class='body'>
				<li>康乃馨</li>
				<li>玫瑰</li>
				<li>百合</li>
				<li>向日葵</li>
				<li>郁金香</li>
				<li>鲜花双拼</li>
				<li>鲜花篮</li>
			</ul>
			
			<!--  -->
			<ul class='body'>
				<li>6枝</li>
				<li>8枝</li>
				<li>12枝</li>
				<li>16枝</li>
				<li>20枝</li>
				<li>22枝</li>
				<li>50枝</li>
				<li>66枝</li>
				<li>99枝</li>
			</ul>
			<!--  -->
			<ul class='body'>
				<li>白色</li>
				<li>红色</li>
				<li>紫色</li>
				<li>蓝色</li>
				<li>粉色</li>
				<li>香槟色</li>
			</ul>
		</view>
		<!-- 内容 -->
		<view class="list_box">
			<view class="list2" v-show="acId==1">
				<view id="demo1" class="scroll-view-item clearfix one" style="background-color: #ffc499;" v-for="(item,index) in list1" :key="index">
					<ul>
						<li>
							<view class="pic-box">
								<image :src="item.src" alt="">
							</view>
							<view class="txt-box">
								<P class="left">
									<p class='span1'>{{item.class}}</p>
									<p  class='left-p'><span class="span3">{{item.money}}</span></p>
								</P>
								<p class="right">
									<text class="btn" @click="btn()">{{item.go}}</text>
								</p>
							</view>
						</li>
					</ul>
				</view>
				<view class="footer">
					没有内容了
				</view>
			</view>
			
			<!-- 第二页 -->
			<view class="list2" v-show="acId==2">
				<view id="demo1" class="scroll-view-item clearfix one" style="background-color: #ffc499;" v-for="(item,index) in list2" :key="item.id">
					<ul>
						<li>
							<view class="pic-box">
								<image :src="item.src" alt="">
							</view>
							<view class="txt-box">
								<P class="left">
									<p class='span1'>{{item.class}}</p>
									<p class='left-p'><text class="span2">{{item.money}}</text> <text class="span3">{{item.money1}}</text> </p>
								</P>
								<p class="right">
									<text class="btn">{{item.go}}</text> 
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
	</view>
</template>

<script>
	export default {

		mounted(){
			
		},
		data() {
			
			return {
				acId:'1',
				list:[
					{id:1,name:"今日商品"},
					{id:2,name:"今日特价"}
				],
				list1:[
					    {
							id:1,
					        src: 'https://img14.360buyimg.com/pop/jfs/t1/191693/27/23755/301333/6265085dEd2ac1f36/e3114358d62584bb.jpg',
					        class: "探病慰问生日鲜花问候长辈12枝郁金香",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:2,
					        src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201809%2F12%2F20180912234205_2i4WT.thumb.700_0.jpeg&refer=http%3A%2F%2Fb-ssl.duitang.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1658049305&t=9035d7c9a1274826ca3bbb54e029642b',
					        class: "探病慰问生日鲜花问候长辈12枝郁金香",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:3,
					        src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fc-ssl.duitang.com%2Fuploads%2Fitem%2F201902%2F09%2F20190209164411_kxWSe.thumb.1000_0.jpeg&refer=http%3A%2F%2Fc-ssl.duitang.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1658049305&t=318b201f912adf05b2c23144456fea11',
					        class: "探病慰问生日鲜花问候长辈6枝郁金香",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:4,
					        src: 'http://t15.baidu.com/it/u=95857463,3184414088&fm=224&app=112&f=JPEG?w=500&h=500',
					        class: "探病慰问生日鲜花问候长辈16枝郁金香",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:5,
					        src: 'http://t15.baidu.com/it/u=3661268364,73524368&fm=224&app=112&f=JPEG?w=350&h=350',
					        class: "探病慰问生日鲜花问候长辈8枝郁金香",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:6,
					        src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201903%2F19%2F20190319091916_eAuT8.thumb.700_0.jpeg&refer=http%3A%2F%2Fb-ssl.duitang.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1658050831&t=18afbbac1dc1c59e7f7b5fb801f19c1e',
					        class: "探病慰问生日鲜花问候长辈20枝郁金香",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:7,
					        src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fci.xiaohongshu.com%2F2e58139a-6b5f-b977-a3e8-36b1691f8587%3FimageView2%2F2%2Fw%2F1080%2Fformat%2Fjpg&refer=http%3A%2F%2Fci.xiaohongshu.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1658050918&t=d4dc6e448ac2b2aeb45c9810112b3809',
					        class: "探病慰问生日鲜花爱情鲜花问候长辈鲜花双拼",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:8,
					        src: 'http://mms1.baidu.com/it/u=3410651056,3423082661&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=667',
					        class: "探病慰问生日鲜花爱情鲜花问候长辈鲜花双拼",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:9,
					        src: 'http://mms1.baidu.com/it/u=727204502,4271864384&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=400&h=533',
					        class: "探病慰问生日鲜花爱情鲜花20枝白色玫瑰花",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:10,
					        src: 'http://mms1.baidu.com/it/u=4250407251,2744147547&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=500',
					        class: "探病慰问生日鲜花问候长辈22枝康乃馨",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:11,
					        src: 'http://mms1.baidu.com/it/u=3020732236,1485778174&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=500',
					        class: "探病慰问生日鲜花问候长辈12枝百合",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:12,
					        src: 'http://mms2.baidu.com/it/u=3975797400,2395426996&fm=253&app=120&f=JPEG&fmt=auto&q=75?w=531&h=500',
					        class: "探病慰问生日鲜花爱情鲜花问候长辈商务用花鲜花篮",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:13,
					        src: 'http://mms0.baidu.com/it/u=3871007375,2462647540&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=500',
					        class: "探病慰问生日鲜花问候长辈8枝康乃馨",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:14,
					        src: 'http://mms1.baidu.com/it/u=2346391171,1314725059&fm=253&app=120&f=JPEG&fmt=auto&q=75?w=500&h=570',
					        class: "探病慰问生日鲜花问候长辈16枝康乃馨",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:15,
					        src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fwww.ebuy16.com%2Fpics%2FO1CN01YSbdWQ28fjGR04nZS%2F3429477960.jpg&refer=http%3A%2F%2Fwww.ebuy16.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1658051444&t=c73ee1cdf01231b43229e1327a59cdaf',
					        class: "探病慰问生日鲜花爱情鲜花问候长辈商务用花鲜花篮",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:16,
					        src: 'http://mms2.baidu.com/it/u=464308951,2606547017&fm=253&app=120&f=JPEG&fmt=auto&q=75?w=500&h=522',
					        class: "探病慰问生日鲜花爱情鲜花6枝蓝色玫瑰花",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:17,
					        src: 'http://mms1.baidu.com/it/u=170027999,1276706958&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=432&h=500',
					        class: "探病慰问生日鲜花爱情鲜花8枝蓝色玫瑰花",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:18,
					        src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fpic2.zhimg.com%2Fv2-c1885630a1bbe45b641d909522dcf191_r.jpg&refer=http%3A%2F%2Fpic2.zhimg.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1658051567&t=da98c7dd7131f7cdd4b4b1c9719b8eb9',
					        class: "探病慰问生日鲜花爱情鲜花22枝蓝色玫瑰花",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:19,
					        src: 'http://mms0.baidu.com/it/u=1895859443,692784830&fm=253&app=120&f=JPEG&fmt=auto&q=75?w=503&h=500',
					        class: "探病慰问生日鲜花爱情鲜花12枝蓝色玫瑰花",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:20,
					        src: 'https://img2.baidu.com/it/u=2963233004,3973766287&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=694',
					        class: "探病慰问生日鲜花爱情鲜花8枝粉色玫瑰花",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:21,
					        src: 'http://mms2.baidu.com/it/u=3326120169,982801159&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=375&h=500',
					        class: "探病慰问生日鲜花爱情鲜花8枝粉色玫瑰花",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:22,
					        src: 'http://mms2.baidu.com/it/u=804704049,1950056946&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=420&h=407',
					        class: "探病慰问生日鲜花爱情鲜花6枝红色玫瑰花",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:23,
					        src: 'http://mms2.baidu.com/it/u=4113884523,3469711457&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=500',
					        class: "探病慰问生日鲜花爱情鲜花16枝红色玫瑰花",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:24,
					        src: 'http://mms0.baidu.com/it/u=395334165,2394259140&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=403&h=541',
					        class: "探病慰问生日鲜花爱情鲜花30枝红色玫瑰花",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:25,
					        src: 'http://mms1.baidu.com/it/u=1907641699,2696299727&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=375&h=499',
					        class: "探病慰问生日鲜花爱情鲜花55枝红色玫瑰花",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:26,
					        src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fp1.meituan.net%2Fdpdeal%2F82876d21a7f3de3e2ab1f27948e52454117015.jpg%2540640w_1024h_1e_1l%257Cwatermark%3D1%26%26r%3D1%26p%3D9%26x%3D2%26y%3D2%26relative%3D1%26o%3D20&refer=http%3A%2F%2Fp1.meituan.net&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1658052066&t=16d3d1fa9c6a2b207970165d0d0d8eba',
					        class: "探病慰问生日鲜花爱情鲜花22枝香槟色玫瑰花",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:27,
					        src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fp0.meituan.net%2Fdpdeal%2F56048831dd9c72e95c61d0cf358c0f1d414652.jpg%2540640w_1024h_1e_1l%257Cwatermark%3D1%26%26r%3D1%26p%3D9%26x%3D2%26y%3D2%26relative%3D1%26o%3D20&refer=http%3A%2F%2Fp0.meituan.net&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1658052101&t=fe2bc88957446da13d49fadee41121a9',
					        class: "探病慰问生日鲜花爱情鲜花20枝香槟色玫瑰花",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:28,
					        src: 'http://mms2.baidu.com/it/u=3440729924,355188624&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=450&h=450',
					        class: "探病慰问生日鲜花爱情鲜花问候长辈6枝向日葵",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:29,
					        src: 'http://mms2.baidu.com/it/u=3707789526,188546141&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=350&h=350',
					        class: "探病慰问生日鲜花爱情鲜花问候长辈3枝向日葵",
					        money: "99.9",
					        go: "去购买"
					    },
					    {
							id:30,
					        src: 'http://mms2.baidu.com/it/u=1348139824,2249825676&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=573',
					        class: "探病慰问生日鲜花爱情鲜花问候长辈12枝向日葵",
					        money: "99.9",
					        go: "去购买"
					    }

					],
				list2:[
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
					{
						id:5,
					    src: 'http://mms2.baidu.com/it/u=3290724860,3578281849&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=500',
					    class: "探病慰问生日鲜花爱情鲜花问候长辈6枝向日葵",
					    money: "99.9",
						money1:'19.9',
					    go: "去购买"
					},
					{
						id:6,
					    src: 'http://mms2.baidu.com/it/u=398204543,2405727028&fm=253&app=138&f=JPEG&fmt=auto&q=75?w=500&h=500',
					    class: "探病慰问生日鲜花爱情鲜花问候长辈22枝郁金香",
					    money: "99.9",
						money1:'19.9',
					    go: "去购买"
					},
				],
				body1:[
					{
						id:1,
						title:'康乃馨'
					},
					{
						id:2,
						title:'玫瑰'
					},
					{
						id:3,
						title:'百合'
					},
					{
						id:4,
						title:'向日葵'
					},
					{
						id:5,
						title:'郁金香'
					},
					{
						id:6,
						title:'鲜花双拼'
					},
					{
						id:7,
						title:'鲜花篮'
					}
				],
				body2:[
					{
						id:1,
						title:'6枝'
					},
					{
						id:2,
						title:'8枝'
					},
					{
						id:3,
						title:'12枝'
					},
					{
						id:4,
						title:'16枝'
					},
					{
						id:5,
						title:'20枝'
					},
					{
						id:6,
						title:'22枝'
					},
					{
						id:7,
						title:'50枝'
					},
					{
						id:8,
						title:'66枝'
					},
					{
						id:9,
						title:'99枝'
					},
				],
				dody3:[
					{
						id:1,
						title:'白色'
					},
					{
						id:2,
						title:'红色'
					},
					{
						id:3,
						title:'紫色'
					},
					{
						id:4,
						title:'蓝色'
					},
					{
						id:5,
						title:'粉色'
					},
					{
						id:6,
						title:'香槟色'
					},
				]
			}
		},
		methods: {
			Taggie(id){
				this.acId = id
			},
			btn(){
				uni.navigateTo({
					url:"../goods/goods"
				})
			}

		}
	}
</script>

<style lang="scss">
	.content {
		padding-bottom:calc(var(-–window-bottom)+30rpx);
	}
	.box{
		width: 100%;
		height: 300rpx;
		background-color: #ffb5a6;
		border-bottom-left-radius: 30%;
		border-bottom-right-radius: 30%;
		padding: 10rpx;
		box-sizing: border-box;
	}
	.nav_box{
		display: flex;
		// margin-top: -400rpx;
		justify-content: space-between;
		width: 94%;
		height: 170rpx;
		margin: -220rpx auto;
		margin-bottom: 0;
		padding: 10rpx;
		box-sizing: border-box;
	}
	.n_left,
	.n_right{
		width: 48%;
		height: 100%;
		font-size: 35rpx;
		/* background-color: #000; */
	}
	.n_left{
		text-align: center;
		image{
			width: 60%;
			height: 100%;
		}
	}
	.n_right{
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		padding: 40rpx 0;
		box-sizing: border-box;
		color: #fff;
	}
	.switch_box{
		width: 94%;
		margin: 0 auto;
		// background-color: #e1a093;
		margin-bottom: 40rpx;
		
		.box_title{
			display: flex;
			justify-content: space-between;
			width: 100%;
			height: 90rpx;
			background-color: #ccc;
			.min_box{
				width: 50%;
				height: 100%;
				background-color: #e1a093;
				text-align: center;
				line-height: 90rpx;
				// font-weight: 600;
				color: #fff;
				font-size: 45rpx
			}
			.active{
				background-color: #f3ad9f;
			}
		}
	}
	.classify{
		width: 95%;
		height: 400rpx;
		margin: 0 auto;

		ul{
			margin: 0;
			padding: 0;
			list-style: none;
			font-size: 35rpx;
			}
			.title{
				width: 20%;
				float: left;
				font-size: 40rpx;
				height: 350rpx;
				li{
					width: 100%;
					height: 33.3%;

				}
			}
			.body{
				width:80% ;
				float: left;
				height: 120rpx;
			li{
				float: left;
				margin-right: 25.5rpx;
				margin-bottom: 20rpx;

			}
			li:hover{
				color: #f3ad9f;
			}
		}
	}

.list_box{
		width: 100%;
		box-sizing: border-box;
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
			margin: 0rpx auto;
			margin-bottom: 30rpx;
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
							width: 100%;
							height: 300rpx;
							image{
							width: 100%;
							height: 100%;
							border-radius: 5%;
							}
						}
						.txt-box{
							padding: 10px 10px;
							width: 100%;
							font-size: 30rpx;
							.left{
								width: 90%;
								.span1{
									width: 100%;
									overflow:hidden;
									text-overflow: ellipsis;
									white-space: nowrap;
								}
								.left-p{
									.span2{									
										color: #ccc;
										text-decoration: line-through;
										font-size: 25rpx;
										}
								
									.span3{
									color: #cc0000;
									text-decoration:none;
									}
								}
							}
							.right{
								height: 75rpx;
								line-height: 75rpx;
								width: 50%;								
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
