<template>
	<div class="list" ref="wrapper">
		<div>
			<div class="area">
				<div class="title border-topbottom">当前城市</div>
				<div class="button-list">
					<div class="button-wrapper">
						<div class="button">{{this.currentCity}}</div>
					</div>
				</div>
			</div>
			<div class="area">
				<div class="title border-topbottom">热门城市</div>
				<div class="button-list">
					<div 
						class="button-wrapper"						
						v-for="item of hotCities"
						:key="item.id"
						@click="handleCityClick(item.name)"
					>
						<div class="button">{{item.name}}</div>
					</div>					
				</div>
			</div>
			<div 
				class="area"
				v-for="(items, key) of cities"
				:key="key"
				:ref="key"
			>
				<div class="title border-topbottom">{{key}}</div>
				<div 
					class="item-list"
					v-for="item of items"
					:key="item.id"
					@click="handleCityClick(item.name)"
				>
					<div class="item border-bottom">{{item.name}}</div>
				</div>
			</div>			
		</div>
	</div>
</template>

<script>
	import BScroll from 'better-scroll'
	import {mapState, mapMutations} from 'vuex'
	export default {
		name: 'CityList',
		props: {
			hotCities: Array,
			cities: Object,
			letter: String
		},
		computed: {
			...mapState({
				currentCity: 'city'
			})
		},
		methods: {
			handleCityClick (city) {
				this.changeCity(city)
				this.$router.push('/')
			},
			...mapMutations(['changeCity'])
		},
		mounted () {
			this.scroll = new BScroll(this.$refs.wrapper)
		},
		watch: {
			letter () {
				if(this.letter){
					const element = this.$refs[this.letter][0]
					this.scroll.scrollToElement(element)
				}
			}
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.border-topbottom
		&:before
			border-color: #ccc
		&:after
			border-color: #ccc
	.border-bottom
		&:before
			border-color: #ccc
	.list
		font-size: .875rem
		overflow: hidden
		position: absolute
		top: 4.6rem
		left: 0
		right: 0
		bottom: 0
		.title
			font-size: .75rem
			line-height: 1rem
			background: #eee
			padding: .5rem 1rem
			color: #666
		.button-list
			overflow: hidden
			padding: .3rem 1.875rem .3rem .3rem
		.button-wrapper
			float: left
			width: 33.33%
			.button
				font-size: .875rem
				text-align: center
				margin: .3rem
				padding: .3rem 0
				border: .06rem solid #ccc
				border-radius: .3rem
		.item-list
			.item
				font-size: .875rem
				line-height: 2.375rem
				padding-left: .6rem
</style>