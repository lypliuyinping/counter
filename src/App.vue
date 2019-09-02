<template>
  <div id="app">
    <input type="text"  class="form-control"  v-model="num"  v-on:input="initalMessage()">
    <counter v-for="n  in parseInt(num)" v-bind:key="n"
    v-on:update='updateNum'
    v-bind:counter="message[n-1]"
     v-bind:index="n"/>
    <p>sum:{{sum}}</p>
    
  </div>
</template>

<script>
//import HelloWorld from "./components/HelloWorld.vue";
import counter from "./components/counter.vue";

export default {
  name: "app",
  components: {
    counter
  },
  data: function() {
    return {
      num: 0,
      message: [],
      sum: 0
    };
  },
  methods: {
    initalMessage: function() {
      let size = parseInt(this.num);
      if (size == 0) {
        this.message = [];
      } else {
        this.message = new Array(size);
        for (let i = 0; i < this.message.length; i++) {
          this.message[i] = i + 1;
        }
      }
      console.log(this.message);
      this.getSum();
    },
    updateNum: function(data) {
      this.message[data.index - 1] = data.value;
      this.getSum();
    },
    getSum: function() {
      this.sum = 0;
      for (var i = 0; i < this.message.length; i++) {
        this.sum += this.message[i];
      }
    }
  }
};
</script>


<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
