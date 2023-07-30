<template>
	<view>
		{{score}}
	</view>
</template>

<script>
	export default {
		data() {
			return {
				score:''
			};
		},
		onLoad(option) {
			//接受分数
			const score = option.type;
			this.score = score
		},
	}
</script>

<style lang="scss">

</style>
