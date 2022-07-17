<template>
  <h2>{{name}}</h2>
 <div>
  <button v-on:mouseover="name = 'Dragonite'"> Cambiar nombre</button>
 </div>

 <h2>{{counter}}</h2>
 <div>
  <button v-on:mouseover="counter += 1">Agregar 1 a la cuenta</button><hr />
  <button v-on:mouseover="counter -= 1">Disminuir 1 a la cuenta</button>
 </div>
<hr />
 <div>
  <button @click="incrementar1"> Agrega 1 usando aumentar1</button>
  <button @click="disminuir1"> Disminuye 1 usando disminuir1</button>
  <button @click="incrementarNum(5)"> Agrega usando incrmentarNum</button>
  <button @click="disminuirNum(5)"> Agrega usando desminuirNum</button>
 
 </div>
  <!--Every single botton goes under a div tag-->
 <div>
  <button @mouseenter="cambiarNombre('Don Cachichurris', $event)" 
  @mouseleave="cambiarNombre('Cabronidas Mendez', $event)">Cambiar el nombre</button>


  </div>




</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      name: 'Davy Jem',
      counter: 0
    }
  },
  methods: {
    cambiarNombre(nam, event){
      this.name = nam
      console.log('Event', event)
    },
   incrementar1(){
    this.counter += 1
   },
   incrementarNum(num){
    this.counter += num
   },
   disminuir1(){
    this.counter -= 1 
   },
   disminuirNum(num){
    this.counter -= num
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
