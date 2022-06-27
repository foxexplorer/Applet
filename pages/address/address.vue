<template>
	<view class="content">
		<view class="add">
			<view @click="add"><text>+</text>新增地址</view>
		</view>
		<view class="have">

			<u-swipe-action>
			  <u-swipe-action-item  v-for="item in list" :key='item.id' :options="options2">
			    <view class="swipe-action u-border-top u-border-bottom">
			      <view class="swipe-action__content">
			        <text class="swipe-action__content__text">
						<text class='one'>{{item.name}}</text>
						<text class='two'>{{item.address}}</text>
					</text>
			      </view>
			    </view>
			  </u-swipe-action-item>
			</u-swipe-action>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:[
					{
						id:1,
						name:'张三',
						address:'xxxxxxxxxxxxxxxxx'
					},
					{
						id:2,
						name:'李四',
						address:'xxxxxxxxxxxxxxxxx'
					}
				],
				options2: [
					 {
						text: '修改',
						style: {
							backgroundColor: '#3c9cff'
						}
					}, 
					{
						text: '删除',
						style: {
							backgroundColor: '#f56c6c'
						}
					},
				],
			}
		},
		methods: {
			add(){
				uni.navigateTo({
					url:'/pages/addTo/addTo'
				})
			}
		}
	}
</script>

<style lang="scss">
.content{
	width: 100%;
	height: 100vh;
	// background-color: #ECF0F2;
}
.add{
	width: 100%;
	padding-top: 100rpx;
	height: 200rpx;
	border-bottom: 1rpx solid #ccc;
	view{
		width: 66%;
		height: 120rpx;
		margin: 0 auto;
		line-height: 120rpx;
		background-color: #fff;
		border: 1rpx solid #f2ad0a;
		border-radius: 60rpx;
		color: #f2ad0a;
		display: flex;
		justify-content: center;
		text{
			color: red;
			font-size: 58rpx;
			// vertical-align: text-top;
		}
	}
}
.have{
	width: 100%;
	}
    .u-page {
        padding: 0;
    }
    .u-demo-block__title {
        padding: 10px 0 2px 15px;
    }

    .swipe-action {
		// margin-top: 40rpx;
        &__content {
             padding: 70rpx 0;
    
            &__text {
                 font-size: 15px;
                 color: $u-main-color;
                 padding-left: 30rpx;
             }
        }
    }
</style>
