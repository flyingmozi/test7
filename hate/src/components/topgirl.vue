<template>
  <div>
    <dl v-for='(item,index) in data' :key="index">
      <dt>
          <img :src="item.Image" alt="">
      </dt>
      <dd>
          <P>{{item.Name}}</P>
          <P>{{item.Introduction}}</P>
          <P class="last"><span>价格：{{item.Price}}</span><s>原价：{{item.LinePrice}}</s></P>
          <button @click='mop(item)'>+</button>
      </dd>
    </dl>
  </div>
</template>

<script>
export default {
  name: "topgirl",
  props: {
    data:Array,
  },
  data(){
      return {
          num:0,
          price:0,
          linprice:0,
      }
  },
  methods:{
      mop(item){
          this.num++;
          this.price+=item.Price;
          this.linprice += item.LinePrice;
          this.$emit('likes',this.num,this.price,this.linprice)
          //console.log(this.price,this.linprice)
      }
  }
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
dl {
  width: 95%;
  height: 140px;
  margin: 10px auto;
  border: 1px solid #ccc;
  display: flex;
  align-items: center;
}
dt{
    width: 130px;
    height: 130px;
    padding-left: 10px;
}
dt>img{
    width: 100%;
    height: 100%;
}
dd{
    flex: 1;
    height: 100%;
    padding: 10px;
}
.last{
    display: flex;
    justify-content: space-between;
    padding: 0 10px;
}
p{
    padding: 0 10px;
    font-size: 13px;
    line-height: 22px;
}
button{
    padding: 3px 10px;
    font-size: 15px;
    margin: 0 50px;
}

</style>