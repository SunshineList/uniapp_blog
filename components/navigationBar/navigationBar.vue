<template>
	<view class="u-page">
		<u-scroll-list :indicator="indicator">
			<u-col span="3" v-for="(item, index) in articleList" :key="index">
				<view class="demo-layout bg-purple">
					<text>{{item.name}}</text>
				</view>
			</u-col>
		</u-scroll-list>
	</view>
</template>

<script>
	export default {
		name: "navigationBar",
		data() {
			return {
				indicator: false,
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
				]
			};
		},
		methods: {
			
		}
	}
</script>

<style lang="scss" scoped>
	.wrap {
		padding: 12px;
	}

	.demo-layout {
		height: 25px;
		border-radius: 4px;
	}

	.bg-purple {
		// background: #;
		background: #f6f5f8;
		text-align: center;
	}

	.bg-purple-light {
		background: #e5e9f2;
	}

	.bg-purple-dark {
		background: #99a9bf;
	}
	
	.u-scroll-list{
		// u-scroll-list__scroll-view__content
		&__scroll-view{
			&__content{
				display: flex;
				justify-content: space-between;
			}
		}
	}
</style>
