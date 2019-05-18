<template>
    <div id="top">
        <span v-for='(item,index) in popstar' :key="index" :class='{active:item.flag}' @click="mvv(item)">{{item.name}}</span>
    </div>
</template>

<script>
    export default {
        props:['popstar','num'],
        data(){
            return{
                flag:false,
            }
        },
        methods:{    
            mvv(item){
                item.flag = !item.flag
            }
        },
        created(){
            this.popstar.forEach(item=>{
                this.$set(item,'flag',false)
            })   
        },
        watch:{
            'num'(news,old){
                this.popstar.forEach(item=>{
                this.$set(item,'flag',false)
            })
            }
        }
    }
</script>

<style scoped>
    span{
        display: inline-block;
        padding: 8px 20px;
        text-align: center;
        border: 1px solid #ccc;
        margin: 5px;
        font-size: 13px;
        border-radius: 45px;
    }
    .active{
        background: rgb(36, 223, 230);
        color: rgb(233, 128, 7);
    }
</style>