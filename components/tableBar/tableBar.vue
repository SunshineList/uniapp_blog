<template>
	<view>
		<u-tabbar :value="value6" @change="name => value6 = name" :fixed="true" :placeholder="true"
			:safeAreaInsetBottom="true">
			<u-tabbar-item text="首页" icon="home"></u-tabbar-item>
			<!-- <u-tabbar-item text="放映厅" icon="photo"></u-tabbar-item> -->
			<!-- <u-tabbar-item text="直播" icon="play-right"></u-tabbar-item> -->
			<u-tabbar-item text="我的" icon="account"></u-tabbar-item>
		</u-tabbar>
	</view>
</template>

<script>
	export default {
		name: "tableBar",
		data() {
			return {
				value6: 0
			};
		}
	}
</script>

<style>

</style>
