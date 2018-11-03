<template>
	<div>
		<div class="title">热销推荐</div>
		<ul>
			<li 
				class="item border-bottom" 
				v-for="item of recommendList"
				:key="item.id"
			>
				<img class="item-img" :src="item.imgUrl">
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-comment">{{item.comment}}条评论</p>
					<p class="item-desc">{{item.desc}}</p>
					<button class="item-button">查看详情</button>
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
	export default {
		name: 'HomeRecommend',
		data () {
			return {
				recommendList: [{
					id: '0001',
					imgUrl: '//img1.qunarzz.com/sight/p0/1810/36/36ed80c6e147d019a3.img.png_280x200_431528fe.png',
					title: '重庆两江夜游',
					comment: '12720',
					desc: '数十里的山城灯海一览无余，“不览夜景，枉到重庆”'
				},{
					id: '0002',
					imgUrl: '//img1.qunarzz.com/sight/p0/1512/44/44e6f0f838b9adc190.water.jpg_280x200_2b203fbf.jpg',
					title: '解放碑步行街',
					comment: '1230',
					desc: '这里是重庆最繁华的商业圈，也是抗战胜利和重庆解放的历史见证'
				},{
					id: '0003',
					imgUrl: '//img1.qunarzz.com/sight/p0/1409/12/ed83b9bb54ccc7ff1f0989a7ebc2e312.jpg_280x200_18f56996.jpg',
					title: '洪崖洞',
					comment: '2290',
					desc: '逛山城老街、观赏两江风光、品尝当地美食的好去处'
				},{
					id: '0004',
					imgUrl: '//img1.qunarzz.com/sight/p0/1803/63/630540ceb7fb0950a3.water.jpg_280x200_682c250a.jpg',
					title: '重庆环球金融中心观景台(会仙楼)',
					comment: '1145',
					desc: '环玻璃幕墙、全露天设计，感受不一样的梦幻重庆'
				},{
					id: '0005',
					imgUrl: '//img1.qunarzz.com/sight/p0/1705/5c/5c00cf8542ccd71ca3.water.jpg_280x200_94fa7fee.jpg',
					title: '朝天门',
					comment: '19',
					desc: '朝天门是一个码头广场，可以看到两种不同颜色的江水交汇'
				},]
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
		text-indent: .3
	.item
		font-size: 14px
		display: flex
		overflow: hidden
		align-items: center
		.item-img
			width: 140px
			height: 100px
			padding: .3rem
		.item-info
			flex: 1
			padding: .3rem
			min-width: 0
			.item-title
				color: #212121
				font-weight: bold
				line-height: 1.2rem
				font-size: 1.2rem
				ellipsis()
			.item-comment
				margin-top: .7rem
			   color: #9e9e9e
			   font-size: .75rem
			   line-height: .75rem
			.item-desc
				padding: .5rem 0
				color: #9e9e9e
				font-size: .8rem
				line-height: .8rem
				ellipsis()
			.item-button
				background: #ff9300
				padding: .1rem .5rem
				border: none
				border-radius: .35rem
				color: #fff
</style>