<template>
	<div>
		<div class="title">周末去哪儿</div>
		<ul>
			<li 
				class="item border-bottom" 
				v-for="item of recommendList"
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
		data () {
			return {
				recommendList: [{
					id: '0001',
					imgUrl: 'http://img1.qunarzz.com/sight/source/1509/d5/82498669f3a48d.jpg_r_640x214_21f7a4ff.jpg',
					title: '重庆两江夜游',
					desc: '数十里的山城灯海一览无余，“不览夜景，枉到重庆”'
				},{
					id: '0002',
					imgUrl: 'http://img1.qunarzz.com/sight/source/1505/53/4bcd11cc3a5374.jpg_r_640x214_988a4cee.jpg',
					title: '重庆必游TOP10',
					desc: '重庆，非去不可'
				},{
					id: '0003',
					imgUrl: 'http://img1.qunarzz.com/sight/source/1505/5f/276ed6784d25ee.jpg_r_640x214_2193082e.jpg',
					title: '重庆优质汤泉',
					desc: '细数重庆那些最赞的温泉'
				},{
					id: '0004',
					imgUrl: 'http://img1.qunarzz.com/sight/source/1505/48/f117e9b3bf582a.jpg_r_640x214_b8145711.jpg',
					title: '重庆大美古镇',
					desc: '行走重庆最美古镇，让你瞬间穿越千年'
				},{
					id: '0005',
					imgUrl: 'http://img1.qunarzz.com/sight/source/1506/1e/f97881dbd07520.jpg_r_640x214_f8c25916.jpg',
					title: '本地人带你耍',
					desc: '玩转小面之都，High翻天'
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