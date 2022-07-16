<template>
  <h2>{{1 + 2 + 3}}</h2>
  <h2>Add method: {{add()}}</h2>
  <h2>Add method by using parameters: {{addParam(3,4,5)}}</h2>
  <h2>Multiplication method {{multiply(baseNumber)}}</h2>

</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      baseMultiplayer: 5,
      baseNumber: 2
    }
  },
  methods: {
    add(){
      return 2+3+4
    },
    addParam(a,b,c){
      return a+b+c
    },
    multiply(num){
      return num * this.baseMultiplayer
    } 

  },
  
}
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
</style>
