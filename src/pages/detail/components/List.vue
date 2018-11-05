<template>
	<div>
		<div 
			class="item" 
			v-for="(item, index) of list"
			:key="index"
		>
			<div class="item-title border-bottom">
				<span class="item-title-icon"></span>
				{{item.title}}
			</div>
			<div class="item-children" v-if="item.children">
				<detail-list :list="item.children"></detail-list>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'DetailList',
		props: {
			list: Array
		}
	}
</script>

<style lang="stylus" scoped>
	.item-title
		line-height: 2.58rem
		padding: 0 .625rem
	.item-title-icon
		position: relative
		left: .2rem
		top: .25rem
		display: inline-block
		width: 1.125rem
		height: 1.125rem
		background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -1.4rem no-repeat
		margin-right: .3rem
		background-size: 1.25rem 9rem
	.item-children
		padding: 0 1rem
</style>