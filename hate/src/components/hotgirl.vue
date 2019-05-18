<template>
    <div class="bottom">
        <div class="left">
            <i class="iconfont icon-gouwuche"></i>
            <b>{{num}}</b>
        </div>
        <div>
            <p>总价：<span>￥ {{price}}</span></p>
            <p>已优惠：<span>￥ {{most-price}}</span></p>
        </div>
    </div>
</template>

<script>
    import '../fonts/iconfont.css'
    export default {
        name:'hopgirl',
        props:{
            num:Number,
            price:Number,
            most:Number
        }
    }
</script>

<style scoped>
    .bottom{
        width: 100%;
        height: 100%;
        display: flex;
    }
    .bottom .left{
        width: 50%;
        text-align: center;
        line-height: 80px;
        position: relative;
    }
    i{
        font-size: 30px;  
    }
    b{
        display: block;
        width: 20px;
        height: 20px;
        border-radius: 50%;
        background: red;
        color: #fff;
        position: absolute;
        top: 20px;
        right:60px;
        text-align: center;
        line-height: 20px;
        font-size: 13px;
    }
    div p{
        font-size: 14px;
        line-height: 30px;
        margin-top: 5px;
    }
    p span{
        color: rgb(221, 116, 18);
    }
</style>