<template>
  <div class="hello">
    <span> {{index}}:</span>
    <button type="submit" v-on:click="add">+</button> 
    <span> {{counter}}</span>
    <button type="submit" @click="minus">-</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    index: Number,
    counter: Number
  },

  methods: {
    add: function() {
      this.counter++;
      this.deliver();
    },
    minus: function() {
      this.counter--;
      this.deliver();
    },

    deliver: function() {
      this.$emit("update", {
        index: this.index,
        value: this.counter
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
