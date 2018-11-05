<template>
	<div>
		<div class="title">热销推荐</div>
		<ul>
			<router-link 
				tag="li"
				class="item border-bottom" 
				v-for="item of list"
				:key="item.id"
				:to="'/detail/' + item.id"
			>
				<img class="item-img" :src="item.imgUrl">
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-comment">{{item.comment}}条评论</p>
					<p class="item-desc">{{item.desc}}</p>
					<button class="item-button">查看详情</button>
				</div>
			</router-link>
		</ul>
	</div>
</template>

<script>
	export default {
		name: 'HomeRecommend',
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