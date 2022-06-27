<template>
	<view class="content">
		<view class="body">
			<ul>
				<li>
					<view>联系人</view>
					<input type="text">

				</li>
				<li>
					<view>手机号码</view>
					<input type="text">
				</li>
				<li>
					<view>请选择地区</view>
					<input type="text">

				</li>
				<li>
					<view>详细地址</view>
					<input type="text">

				</li>
				<li style='border-bottom: none;'>
					<view>邮政编码</view>					
					<input type="text">

				</li>
			</ul>
			<view class="foot">
				<u-button style='border: none;' text="保存" type='error' @click='add'></u-button>
				<u-button text="取消" type='info'></u-button>
			</view>
		</view>
		<u-modal :show="show"
		 ref="uModal"
		 :closeOnClickOverlay='true'
		 :showConfirmButton='false'
		  :asyncClose="true"
		  width='350rpx'
		  @close='close'>添加成功</u-modal>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:false
			}
		},
		methods: {
			add(){
				this.show = true

			},
			close(){
				this.show = false
				uni.navigateTo({
					url:'/pages/address/address'
				})
			}
		}
	}
</script>

<style lang="scss">
	.content{
		background-color: #ECF0F2;
		height: 100vh;
	}
.body{
	width: 100%;
	background-color: #fff;
	padding-bottom: 30rpx;
	ul{
		list-style: none;
		margin: 0;
		padding: 0;
		li{
			display: flex;
			justify-content: space-between;
			height: 70rpx;
			line-height: 70rpx;
			padding: 20rpx;
			border-bottom: 1rpx solid #ccc;
			// background-color: #0cff59;
			input{
				width: 75%;
				height: 70rpx;
				// border: 1rpx solid #ccc;
			}
		}
	}
	.foot{
		width: 90%;
		margin: 30rpx auto;
	}
}
</style>
