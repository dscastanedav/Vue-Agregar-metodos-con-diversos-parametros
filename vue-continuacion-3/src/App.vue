<template>

  <h2>Full name: {{firstName}} {{lastName}}</h2>
  <h2>Computed full name: {{fullName}} </h2>
  <!--La forma de abajo no es correcta porque no ayuda a la reutilizacion del codigo
  en lugar de eso toca mantenerlo diferente en cada lado que se quiera usar-->

  <!--<h2>Total: {{items.reduce((total, curr) => (total += curr.price), 0)}}</h2>-->
  
  <button @click="items.push({id:'4', title:'keyboard',price:400})">Add item</button>

  <h2>Total using computed propertie: {{totalComputed}}</h2>

  <h2>Total using method: {{getTotal()}}</h2>

  <input type="text" v-model="country" >

  <template v-for="item in items" :key="item.id">
    <h2 v-if="item.price > 100">{{item.title}} {{item.price}}</h2>
  </template>
  
  <h2 v-for="item in expensiveItems" :key="item.id">{{item.title}} {{item.price}}</h2>

</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      firstName: 'Davy',
      lastName: 'Jem',
      items: [
        {
          id: 1,
          title: 'TV',
          price: 100
        },
        {
          id: 2,
          title: 'Phone',
          price: 200
        },
        {
          id: 3,
          title: 'Laptop',
          price: 300
        }
      ],
      country: ''
    }
  },
  methods: {
    getTotal(){
      console.log('getTotal method')
      return this.items.reduce((total, curr) => (total = total + curr.price), 0)
    }

  },
  computed:{
    fullName(){
      return `${this.firstName} ${this.lastName}`
    },
    totalComputed(){
      console.log('totalComputed propertie')
      return this.items.reduce((total, curr) => (total = total + curr.price), 0)
    },
    expensiveItems(){
      return this.items.filter(item => item.price > 100)
    }
  }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
.underline {
  text-decoration: underline;
}
.promoted {
  font-style: italic;
}
.new {
  color: olivedrab;
}
.sold-out {
  color: red;
}
label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}
input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}
input[type='text'],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
