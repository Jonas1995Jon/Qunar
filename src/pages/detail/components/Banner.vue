<template>
	<div>
		<div class="banner" @click="handleBannerClick">
			<img class="banner-img" :src="bannerImg">
			<div class="banner-info">
				<div class="banner-title">{{sightName}}</div>
				<div class="banner-number">
					<span class="iconfont banner-icon">&#xe678;</span>
					{{gallaryImgs.length}}
				</div>
			</div>
		</div>
		<common-fade>
			<common-gallary 
				:imgs="gallaryImgs" 
				v-show="showGallary"
				@close="handleGallaryClose"
			></common-gallary>
		</common-fade>
	</div>
</template>

<script>
	import CommonGallary from 'common/gallary/Gallary'
	import CommonFade from 'common/fade/Fade'
	export default {
		name: 'DetailBanner',
		props: {
			sightName: String,
			bannerImg: String,
			gallaryImgs: Array
		},
		data () {
			return {
				showGallary: false
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
			CommonGallary,
			CommonFade
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