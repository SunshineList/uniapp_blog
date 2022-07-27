<template>
	<view>
		<u-scroll-list :indicator="indicator">
			<u-row justify="space-between">
				<u-col span="3" v-for="(item, index) in articleList" :key="index">
					<view class="demo-layout bg-purple" @click="clickCategory(item.id, index)">
						<text :class="nowIndex == index ? 'click_class' : '' ">{{item.name}}</text>
					</view>
				</u-col>
			</u-row>
		</u-scroll-list>
		
		<view class="uni-list">
			<view class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(item,index) in list" :key="index">
				<view class="uni-media-list">
					<image class="uni-media-list-logo" :src="item.author_avatar"></image>
					<view class="uni-media-list-body">
						<view class="uni-media-list-text-top">{{item.title}}</view>
						<view class="uni-media-list-text-bottom uni-ellipsis">{{item.summary}}</view>
					</view>
				</view>
			</view>
		</view>
		<!-- <uni-table stripe emptyText="暂无更多数据">
			<uni-tr>
				<uni-th align="center"></uni-th>
			</uni-tr>
			<uni-tr>
				<uni-td></uni-td>
			</uni-tr>
		</uni-table> -->
	</view>
</template>

<script>
	export default {
		name: "navigationBar",
		data() {
			return {
				indicator: false,
				nowIndex: 0,
				list: [],
				textClass: "",
				articleList: [{
						"id": 1,
						"name": "军事"
					},
					{
						"id": 2,
						"name": "游戏"
					},
					{
						"id": 3,
						"name": "影视"
					},
					{
						"id": 4,
						"name": "娱乐"
					},
					{
						"id": 5,
						"name": "科技"
					},
					{
						"id": 6,
						"name": "汽车"
					},
					{
						"id": 7,
						"name": "汽车"
					},
				]
			};
		},
		
		created() {
			uni.showLoading({
				title: "加载中...."
			})
			uni.request({
				url: 'https://unidemo.dcloud.net.cn/api/news',
				method: 'GET',
				data: {},
				success: res => {
					this.list = res.data
					uni.hideLoading()
				},
				fail: () => {},
				complete: () => {}
			});
		
		},
		
		methods: {
			clickCategory(categoryId, index) {
				if (this.nowIndex == index) {
					return // 如果点击的时候发现id和本次id一致就不请求数据
				}
				this.nowIndex = index
			}
		}
	}
</script>

<style lang="scss" scoped>
	.wrap {
		padding: 12px;
	}

	.click_class {
		// font-size: 48rpx;
		font-weight: bolder;
		color: red;
	}

	.demo-layout {
		height: 25px;
		border-radius: 4px;
	}

	.bg-purple {
		// background: #;
		background: lightcyan;
		// background: red;
		text-align: center;
		// padding-left: 20rpx;
		margin-left: 8rpx;
	}

	.bg-purple-light {
		background: #e5e9f2;
	}

	.bg-purple-dark {
		background: #99a9bf;
	}
	
	.uni-media-list-body{
		height: auto;
		line-height: 1.6em;
	}
	
</style>
