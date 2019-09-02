<template>
  <div class="hello">
    <button type="submit" @click="add">+</button> 
    <button type="submit" @click="minus">-</button>
    <p> {{message}}</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
         data:function(){
                return{
                    message:0
                }
            },
          methods:{
            add:function () {
                    this.message++;
                console.log(this.message);
            },
            minus:function () {
                    this.message--;
            }
    }
}
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
