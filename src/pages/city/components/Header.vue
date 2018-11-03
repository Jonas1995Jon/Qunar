<template>
	<div class="header">
		<router-link to="/">
			<span class="iconfont header-back">&#xe624;</span>
		</router-link>
		城市选择
	</div>
</template>

<script>
	export default {
		name: 'CityHeader',
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.header
		font-size: 1rem
		overflow: hidden
		height: $headerHright
		line-height: $headerHright
		text-align: center
		color: #fff
		background: $bgColor
		position: relative
		.header-back
			width: $headerHright
			height: $headerHright
			line-height: $headerHright
			position: absolute
			left: 0
			color: #fff
</style>