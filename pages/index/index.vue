<template>
	<view>
		<navigationBar></navigationBar>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				name: 0,
			}
		},
		methods: {
			getCategoryList(id){
				console.log(id);
			}
		}
	}
</script>

<style lang="scss">
	
</style>
