<template>
	<div class="header">
		<div class="header-left">
			<span class="iconfont">&#xe624;</span>
		</div>
		<div class="header-input">
			<span class="iconfont">&#xe632;</span>
			输入城市/景点/游玩主题
		</div>
		<router-link to="/city">
			<div class="header-right">
				{{this.city}}
				<span class="iconfont arrow-icon">&#xe64a;</span>
			</div>
		</router-link>
	</div>
</template>

<script>
	import {mapState, mapGetters} from 'vuex'
	export default {
		name: 'HomeHeader',
		computed: {
			...mapState(['city']),
			...mapGetters(['doubleCity'])
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.header
		display: flex
		color: white
		font-size: 14px
		line-height: $headerHright
		background: $bgColor
		.header-left
			text-align: center
			width: $headerHright
			float: left
		.header-input
			color: #DBDBDBFF
			flex: 1
			line-height: 2rem
			margin: auto 0
			padding-left: .5rem
			background: white
			border-radius: .2rem
		.header-right
			min-width: 3.5rem
			padding: 0 .3125rem
			float: right
			text-align: center
			color: #fff
			.arrow-icon
				font-size: 10px
				margin-left: -2px
</style>