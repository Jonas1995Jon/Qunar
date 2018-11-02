<template>
	<div class="icons">
		<swiper>
			 <swiper-slide v-for="item of iconList" :key="item.id">
				<div class="icon">
					<div class="icon-img">
						<img class="icon-img-content" :src="item.imgUrl">
					</div>
					<p class="icon-desc">{{item.imgTitle}}</p>
				</div>
			</swiper-slide>
		</swiper>
	</div>
</template>

<script>
	export default {
		name: 'HomeIcons',
		data () {
			return {
				iconList: [{
					id: '0001',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					imgTitle: '景点门票'
				},
				{
					id: '0002',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
					imgTitle: '游乐场'
				},
				{
					id: '0003',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
					imgTitle: '重庆必游'
				},
				{
					id: '0004',
					imgUrl: 'https://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
					imgTitle: '打卡圣地'
				},
				{
					id: '0005',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
					imgTitle: '一日游'
				},
				{
					id: '0006',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/89/55083b0f1951f302.png',
					imgTitle: '两江夜游'
				},
				{
					id: '0007',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png',
					imgTitle: '神秘武隆'
				},
				{
					id: '0008',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
					imgTitle: '泡温泉'
				}]
			}
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.icons >>> .swiper-container
		font-size: 12px
		height: 0
		padding-bottom: 50%
	.icon
		position: relative
		overflow: hidden
		float: left
		width: 25%
		height: 0
		padding-bottom: 25%
		.icon-img
			position: absolute
			top: 0
			left: 0
			right: 0
			bottom: 20px
			box-sizing: border-box
			.icon-img-content
				display: block
				margin: 0 auto
				height: 100%
		.icon-desc
			position: absolute
			left: 0
			right: 0
			bottom: 0
			height: 1.25rem
		    text-align: center
		    line-height: 1.25rem
</style>