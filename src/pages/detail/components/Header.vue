<template>
	<div>
		<router-link 
			class="header-abs"
			tag="div" 
			to="/" 
			v-show="showAbs"
		>
			<span class="iconfont header-abs-back">&#xe624;</span>
		</router-link>
		<div 
			class="header-fixed" 
			v-show="!showAbs"
			:style="opacityStyle"
		>
			<router-link tag="div" to="/">
				<span class="iconfont header-fixed-back">&#xe624;</span>
				景点详情
			</router-link>
		</div>
	</div>
</template>

<script>
	import CommonGallary from 'common/gallary/Gallary'
	export default {
		name: 'DetailHeader',	
		data () {
			return {
				showAbs: true,
				opacityStyle: {
					opacity: 0
				}
			}
		},
		methods: {
			handleScroll () {
				const top = document.documentElement.scrollTop
				if(top > 40){
					let opacity = top / 140
					opacity = opacity > 1 ? 1 : opacity
					this.opacityStyle = {
						opacity
					}
					this.showAbs = false
				} else {
					this.showAbs = true
				}
			}
		},
		mounted () {
			window.addEventListener('scroll', this.handleScroll)
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.header-abs
		position: absolute
		left: .625rem
		top: .625rem
		width: 2rem
		height: 2rem
		line-height: 2rem
		text-align: center
		border-radius: 1rem
		background: rgba(0, 0, 0, .8)
		.header-abs-back
			color: #fff
			font-size: .5rem
	.header-fixed
		position: fixed
		top: 0
		left: 0
		right: 0
		font-size: 1rem
		height: $headerHright
		line-height: $headerHright
		text-align: center
		color: #fff
		background: $bgColor
		.header-fixed-back
			width: $headerHright
			height: $headerHright
			line-height: $headerHright
			position: absolute
			left: 0
			color: #fff
</style>