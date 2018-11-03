<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <swiper-slide v-for="item of swiperList" :key="item.id">
                <img class="swiper-image" :src="item.imgUrl" />
            </swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
        swiperOption: {
            pagination: '.swiper-pagination',
            loop: true
        },
        swiperList: [{
            id: '0001',
            imgUrl: 'https://img1.qunarzz.com/qs/1809/64/62160a38d119c202.jpg'
        },{
            id: '0002',
            imgUrl: 'https://img1.qunarzz.com/qs/1811/3f/85a00499e2e0802.jpg'
        },{
            id: '0003',
            imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/2d/0d7dc3400a50b502.jpg_750x200_4ca95dd4.jpg'
        },{
            id: '0004',
            imgUrl: 'http://img1.qunarzz.com/piao/fusion/1810/6e/4a5551bbb189d902.jpg_750x200_25257467.jpg'
        },{
            id: '0005',
            imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/c6/2467595fffc3b302.jpg_750x200_cca13d51.jpg'
        }]
    }
  }
}

</script>
<style lang="stylus" scoped>
    .wrapper >>> .swiper-pagination-bullet-active
        background: #fff
    .wrapper
        overflow: hidden
        width: 100%
        height: 0
        padding-bottom: 26%
        background: #eee
        .swiper-image
            width: 100%
</style>
