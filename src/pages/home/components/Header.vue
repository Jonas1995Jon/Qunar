<template>
	<div class="header">
		<div class="header-left">
			<span class="iconfont">&#xe624;</span>
		</div>
		<div class="header-input">
			<span class="iconfont">&#xe632;</span>
			输入城市/景点/游玩主题
		</div>
		<div class="header-right">
			城市
			<span class="iconfont arrow-icon">&#xe64a;</span>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'HomeHeader'
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.header
		display: flex
		color: white
		font-size: 14px
		line-height: 2.5rem
		background: $bgColor
		.header-left
			text-align: center
			width: 2.5rem
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
			width: 3.5rem
			float: right
			text-align: center
			.arrow-icon
				font-size: 10px
				margin-left: -2px
</style>