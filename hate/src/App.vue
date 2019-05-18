<template>
  <div id="app">
      <header class="header">超级卖场</header>
      <div class="main">
          <topgirl :data='list' @likes = 'mun'></topgirl>
      </div>
      <footer class="footer">
          <hotgirl :num='num' :price='price' :most='linprice'></hotgirl>
      </footer>
  </div>
</template>

<script>

import topgirl from './components/topgirl'
import hotgirl from './components/hotgirl'

export default {
  created() {
    this.list = require('./list.json')
  },
  name: "App",
  components: {
    topgirl,
    hotgirl,
  },
  data() {
    return {
      list:[],
      num:0,
      price:0,
      linprice:0,
    };
  }, 
  methods:{
    mun(num,price,linprice){
        this.num = num;
        this.price = price;
        this.linprice = linprice;
        //console.log(this.num,this.price,this.linprice)
    }
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
html,
body,
#app {
  width: 100%;
  height: 100%;
}
#app {
  display: flex;
  width: 100%;
  flex-direction: column;
}
.header{
    width: 100%;
    height: 44px;
    text-align: center;
    line-height: 44px;
    font-size: 20px;
}
#app .main{
    flex: 1;
    width: 100%;
    overflow: auto;
}
.footer{
    width: 100%;
    height: 80px;
    border-top: 1px solid #ccc;
}

</style>
