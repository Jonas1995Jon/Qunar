<template>
	<div class="search">
		<input class="search-input" type="text" name="search" placeholder="输入城市名或拼音">
	</div>
</template>

<script>
	export default {
		name: 'CitySearch',
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.search
		height: 2rem
		padding: 0 .8rem
		background: $bgColor
		.search-input
			box-sizing: border-box
			width: 100%
			height: 1.5rem
			padding: 0 .5rem
			line-height: 1rem
			text-align: center
			border-radius: .5rem
			color: #666
</style>