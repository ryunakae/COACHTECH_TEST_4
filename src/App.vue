<template>
  <div id="app">
    <div>
      <input type="number" v-model="n">
      <button @click="leapYear">調べる</button>
      <p>{{message}}</p>
    </div>
    <div class="contener">
      <p @mouseover="hover" @mouseleave="leave">アコーディオン</p>
      <div v-if="hoverFlag">
        アコーディオンの中身が入ります。
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
  },
  data() {
    return {
      message: "閏年かどうかを判定します",
      n: "",
      hoverFlag: false,
    };
  },
  methods: {
    hover(){
      this.hoverFlag = true
    },
    leave(){
      this.hoverFlag = false
    },
    leapYear() {
      if (this.n % 4 == 0 && this.n % 100 !== 0 || this.n % 400 == 0) {
        this.message = "閏年"
        console.log("閏年")
      }
      else {
        this.message = "閏年ではない"
      }
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.contener {
  border: solid 1px;
  width: 400px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
}
.contener p {
  background-color: #d4d4d4;
  margin: 0;
  padding: 10px;
  font-size: 24px;
}
.contener div {
  line-height: 100px;
}
</style>
