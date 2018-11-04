<template>
	<ul class="list">
		<li 
			class="item"			
			v-for="(item, key) of cities"
			:key="key"
		>
			{{key}}
		</li>
	</ul>
</template>

<script>
	export default {
		name: 'CityAlphabet',
		props: {
			cities: Object
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.list
		font-size: .875rem
		display: flex
		flex-direction: column
		justify-content: center
		position: absolute
		top: 4.3rem
		right: 0
		bottom: 0
		width: 1rem
		.item
			line-height: 1.4rem
			text-align: center
			color: $bgColor
</style>