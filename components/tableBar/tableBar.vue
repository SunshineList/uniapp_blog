<template>
	<view>
		<u-tabbar :value="tabIndex" :fixed="true" :placeholder="true" :safeAreaInsetBottom="true">
			<u-tabbar-item text="首页" icon="home" @click="jumpIndex"></u-tabbar-item>
			<u-tabbar-item text="我的" icon="account" @click="jumpProfile"></u-tabbar-item>
		</u-tabbar>
	</view>
</template>

<script>
	export default {
		name: "tableBar",
		props: {
			tabIndex: {
				type: Number,
				default: 0
			}
		},
		data() {
			return {
				
			};
		},
		methods: {
			// changeIndex(name) {
			// 	this.tabIndex = name
			// },
			jumpIndex(name) {
				uni.redirectTo({
					url: "/pages/index/index"
				})
			},
			jumpProfile(name) {
				uni.redirectTo({
					url: "/pages/profile/profile"
				})
			}
		}
	}
</script>

<style>

</style>
