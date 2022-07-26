<template>
	<view class="content">
		<tableBar></tableBar>
		<u--text type="primary" text="主色"></u--text>
		<u--text type="error"   text="错误"></u--text>
		<u--text type="success" text="成功"></u--text>
		<u--text type="warning" text="警告"></u--text>
		<u--text type="info"    text="信息"></u--text>
		<!-- <image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		padding-left: 40rpx;
		display: flex;
		justify-content: space-between;
	}
</style>
