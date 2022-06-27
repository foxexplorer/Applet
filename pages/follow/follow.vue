<template>
	<view class="content">
			<u-index-list :index-list="indexList">
				<template v-for="(item, index) in itemArr">
					<!-- #ifdef APP-NVUE -->
					<u-index-anchor :text="indexList[index]"></u-index-anchor>
					<!-- #endif -->
					<u-index-item>
						<!-- #ifndef APP-NVUE -->
						<u-index-anchor :text="indexList[index]"></u-index-anchor>
						<!-- #endif -->
						<view class="list-cell" v-for="(cell, index) in item">
							{{cell}}
						</view>
					</u-index-item>
				</template>
			</u-index-list>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				indexList: ["A", "B", "C","D","E","F","G","H","I","J","K","L","M","N","O","P","Q","I","S","T","U","V","W","X","Y","Z"],
								itemArr: [
									[''],// A列表
									['百合'],//B列表
									[''],//C列表
									[''],//D列表
									[''],//E列表
									[''],//F列表
									[''],//G列表
									[''],//H列表
									[''],//I列表
									[''],//J列表
									['康乃馨'],//K列表
									[''],//l列表
									['玫瑰'],//m列表
									[''],//n列表
									[''],//O列表
									[''],//P列表
									[''],//Q列表
									[''],//R列表
									[''],//S列表
									[''],//T列表
									[''],//U列表
									[''],//V列表
									[''],//W列表
									['向日葵','鲜花篮','鲜花双拼'],//X列表
									['郁金香'],//Y列表
									[''],//Z列表
								]
			}
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
