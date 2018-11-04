<template>
	<div>
		<div class="search">
			<input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音">
		</div>
		<div 
			class="search-content" 
			ref="search"
			v-show="keyword"
		>
			<ul>
				<li 
					class="search-item border-bottom" 
					v-for="item of list"
					:key="item.id"
					@click="handleCityClick(item.name)"
				>
					{{item.name}}
				</li>
				<li 
					class="search-item border-bottom"
					v-show="hasNoData"
				>
					没有找到匹配数据
				</li>
			</ul>
		</div>		
	</div>
</template>

<script>
	import BScroll from 'better-scroll'
	import {mapMutations} from 'vuex'
	export default {
		name: 'CitySearch',
		props: {
			cities: Object
		},
		data () {
			return {
				keyword: '',
				list: [],
				timer: null
			}
		},
		methods: {
			handleCityClick (city) {
				this.changeCity(city)
				this.$router.push('/')
			},
			...mapMutations(['changeCity'])
		},
		computed: {
			hasNoData () {
				return !this.list.length
			}
		},
		watch: {
			keyword () {
				if(!this.keyword){
					this.list = []
					return
				}
				if(this.timer){
					clearTimeout(this.timer)
				}
				this.timer = setTimeout(() => {
					const result = []
					for (let i in this.cities) {
						this.cities[i].forEach((value) => {
							if(value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1){
								result.push(value)
							}
						});
					}
					this.list = result
				}, 100)
			}
		},
		mounted () {
			this.scroll = new BScroll(this.$refs.search)
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.search
		height: 1.8rem
		padding: 0 .6rem
		background: $bgColor
		.search-input
			box-sizing: border-box
			width: 100%
			height: 1.5rem
			padding: 0 .5rem
			line-height: 1rem
			text-align: center
			border-radius: .3rem
			color: #666
	.search-content
		z-index: 1
		overflow: hidden
		position: absolute
		top: 4.3rem
		left: 0
		right: 0
		bottom: 0
		background: #eee
		.search-item
			line-height: 2rem
			padding-left: .625rem
			background: #fff
			color: #666
</style>