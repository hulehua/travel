<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div
          class="icon"
          v-for="item of page"
          :key="item.id"
        >
          <div class='icon-img'>
            <img class='icon-img-content' :src='item.imgUrl' />
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
    data() {
        return {
            swiperOption: {
                autoplay: false
            },
            iconsList: [{
                id:'001',
                desc:'热门景点',
                imgUrl:'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png'
            } , {
                id:'002',
                desc:'酒店',
                imgUrl:'http://s.qunarzz.com/homenode/images/touchheader/hotel.png'
            } , {
                id:'003',
                desc:'机票',
                imgUrl:'http://s.qunarzz.com/homenode/images/touchheader/flight.png'
            } , {
                id:'004',
                desc:'度假',
                imgUrl:'http://s.qunarzz.com/homenode/images/touchheader/package.png'
            } , {
                id:'005',
                desc:'火车票',
                imgUrl:'http://s.qunarzz.com/homenode/images/touchheader/train.png'
            } , {
                id:'006',
                desc:'景点门票',
                imgUrl:'http://s.qunarzz.com/homenode/images/touchheader/piao.png'
            } , {
                id:'007',
                desc:'民宿客栈',
                imgUrl:'http://s.qunarzz.com/homenode/images/touchheader/innBnb.png'
            } , {
                id:'008',
                desc:'低价机票',
                imgUrl:'http://s.qunarzz.com/homenode/images/touchheader/bargainflight.png'
            } , {
                id:'009',
                desc:'特惠酒店',
                imgUrl:'http://s.qunarzz.com/homenode/images/touchheader/group.png'
            }]
        }
    },
    computed: {
         pages () {
            const pages = []
            this.iconsList.forEach((item, index) => {
                const page = Math.floor(index / 8)
                if (!pages[page]) {
                    pages[page] = []
                }
                pages[page].push(item)
            })
            return pages
            }
    },
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
    .icons
        width: 100%
        overflow: hidden
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
                bottom: .44rem
                .icon-img-content
                    display: block
                    margin: 0 auto
                    height: 100%
            .icon-desc
                position: absolute
                left: 0
                right: 0
                bottom: 0
                height: .44rem
                line-height: .44rem
                text-align: center
                color: #333
</style>
