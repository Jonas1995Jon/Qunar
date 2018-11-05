<template>
	<div>
		<div class="banner" @click="handleBannerClick">
			<img class="banner-img" src="//img1.qunarzz.com/sight/p0/1810/36/36ed80c6e147d019a3.img.png_600x330_e27d197e.png">
			<div class="banner-info">
				<div class="banner-title">重庆两江夜游</div>
				<div class="banner-number">
					<span class="iconfont banner-icon">&#xe678;</span>
					34
				</div>
			</div>
		</div>
		<common-gallary 
			:imgs="imgs" 
			v-show="showGallary"
			@close="handleGallaryClose"
		></common-gallary>
	</div>
</template>

<script>
	import CommonGallary from 'common/gallary/Gallary'
	export default {
		name: 'DetailBanner',
		data () {
			return {
				showGallary: false,
				imgs: ['http://img1.qunarzz.com/sight/p0/1810/36/36ed80c6e147d019a3.img.png_r_800x800_70a08295.png', 'http://img1.qunarzz.com/sight/p0/1607/e8/e886cc6cacb442ba2e.img.jpg_r_800x800_3287c11b.jpg']
			}
		},
		methods: {
			handleBannerClick () {
				this.showGallary = true
			},
			handleGallaryClose () {
				this.showGallary = false
			}
		},
		components: {
			CommonGallary
		}
	}
</script>

<style lang="stylus" scoped>
	.banner
		position: relative
		overflow: hidden
		height: 0
		padding-bottom: 55%
		.banner-img
			width: 100%
		.banner-info
			display: flex
			align-items: center
			position: absolute
			left: 0
			right: 0
			bottom: 0
			line-height: 1.875rem
			color: #fff
			.banner-title
				flex: 1
				font-size: 1.125rem
				padding: 0.2rem .625rem
				background-image: linear-gradient(to bottom,rgba(0, 0, 0, 0),rgba(0, 0, 0, .8))
			.banner-number
				// position: absolute
				// top: -1.25rem
				// left: .625rem
				font-size: .75rem
				padding: 0 1rem
				line-height: 1.25rem
				height: 1.25rem
				border-radius: .625rem
				background: rgba(0, 0, 0, .5)
				.banner-icon
					font-size: .75rem
</style>