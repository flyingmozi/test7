<template>
  <div id="app">
    <div class="left">
      <p v-for="(item,index) in proviens" :key="index" @click='mvp(index)' :class='{active:index == num}'>{{item.name}}</p>
    </div>
    <div class="right">
      <lokeen :popstar = 'proviens[num].cities' :num='num'></lokeen>
    </div>
  </div>
</template>

<script>
import lokeen from "./components/lokeen";

export default {
  created() {
    this.proviens = require("./city.json");
  },
  name: "App",
  components: {
    lokeen
  },
  data() {
    return {
      num: 0,
      proviens: []
    };
  },
  methods:{
    mvp(index){
      this.num = index
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
}
.left {
  width: 30%;
  height: 100%;
  overflow: auto;
}
.left p {
  width: 75px;
  height: 35px;
  line-height: 30px;
  text-align: center;
  font-size: 14px;
  border: 1px solid #ccc;
  margin: 10px auto;
}
.right {
  flex: 1;
  height: 100%;
}
.active {
  background: rgb(236, 213, 82);
  color: #fff;
}
</style>
