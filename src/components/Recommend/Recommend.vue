<template>
    <div class="recommend-view">
        <header>{{recommends.title}}</header>
        <div class="content">
            <div class="item" v-for="(item,index) in recommends.list" :key="index">
                <div class="img-wrap">
                    <img :src="item.img_url" alt="">
                </div>
                <div class="content-wrap">
                    <div class="title">{{item.title}}</div>
                    <div class="price-wrap">
                        <span class="sale_price">￥{{item.sale_price}}</span>
                        <span class="list_price">￥{{item.list_price}}</span>
                    </div>
                    <div class="count">{{item.sales}}人付款</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props:{
            recommends:Object, // 推荐描述对象
        }
    }
</script>

<style lang="stylus" rel="stylesheet/stylus">
    @import "../../assets/css/mixins.styl"

    .recommend-view
        background-color #fff
        >header
            padding-top .4rem
            height 1.2rem
            font-size .8rem
            color #333
            text-align center
        .content
            display flex
            justify-content space-between
            flex-wrap wrap
            padding 0 .4rem
            .item
                width 49%
                margin .4rem 0
                border-1px(#ececec)
                .img-wrap
                    img
                        box-sizing border-box
                        border-1px(#ececec)
                        width 100%
                .content-wrap
                    padding 0 .2rem .4rem
                    .title
                        more-wrap(2)
                        font-size .6rem
                        color #333
                    .price-wrap
                        .sale_price
                            font-size .75rem
                            color #e91500
                        .list_price
                            font-size .6rem
                            color #bbb
                            text-decoration line-through
                    .count
                        font-size .6rem
                        color #333
</style>