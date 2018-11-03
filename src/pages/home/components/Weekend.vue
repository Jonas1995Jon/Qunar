<template>
	<div>
		<div class="title">周末去哪儿</div>
		<ul>
			<li 
				class="item border-bottom" 
				v-for="item of list"
				:key="item.id"
			>
				<div class="item-img-wrapper">
					<img class="item-img" :src="item.imgUrl">				
				</div>
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
	export default {
		name: 'HomeWeekend',
		props: {
			list: Array
		},
		data () {
			return {
				
			}
		}
	}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
	.title
		font-size: .8rem
		margin-top: .2rem
		line-height: 2rem
		background: #eee
		text-indent: .3rem
	.item-img-wrapper
		width: auto
	.item-img
		width: 100%
	.item-info
		padding: .4357rem .625rem .625rem .625rem
		min-width: 0
		.item-title
			padding-right: 4.375rem
			color: #212121
			font-size: .875rem
			line-height: 1.5rem
			ellipsis()
		.item-desc
			padding-right: 4.375rem;
			color: #616161;
			font-size: .75rem;
			line-height: 1.3125rem;
			ellipsis()
</style>