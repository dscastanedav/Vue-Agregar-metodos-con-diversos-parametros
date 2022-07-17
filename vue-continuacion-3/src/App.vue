<template>
  <div>
    <pre>
      {{ JSON.stringify(formValues, null, 2) }}
    </pre>
  </div>

  <!--<form @submit="submitForm">-->
  <form @submit.prevent="submitForm2">
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model.trim.lazy="formValues.name">
    </div>
    
    <div>
      <label for="profile">Profile Summary</label>
      <textarea id="profile" v-model="formValues.profileSummary" />  
    </div>

    <div>
      <label for="country">Country</label>
      <select id="country" v-model="formValues.country">
        <option value="">Select an option</option>
        <option value="Locombia">Locombia</option>
        <option value="Polombia">Polombia</option>
        <option value="Colombia">Colombia</option>
        <option value="colombiaconp">Esa Colombia con P mayuscula</option>
      </select>
    </div>

    <div>
      <label for="platillo">Platillo</label>
      <select id="platillo" multiple v-model="formValues.platillo">
        <option value="cafe">Cafe</option>
        <option value="pastalofra">Pastalofra</option>
        <option value="sopa">Sopa</option>
        <option value="torta">Torta</option>
      </select>
    </div>

    <div>
      <input type="checkbox" id="remote" v-model="formValues.remote">
      <label for="remote"> Are you willing to work remotely?</label>
    </div>

    <div>
      <input type="checkbox" id="estupidity" v-model="formValues.estupidez" true-value="si" false-value="no">
      <label for="estupidity"> Es usted estupido?</label>
    </div>


    <div>
      <label>Skill set</label>
      <input type="checkbox" id="html" value="html" v-model="formValues.setSkills">
      <label for="html">Html 5</label>
      <input type="checkbox" id="css" value="css" v-model="formValues.setSkills">
      <label for="css">CSS</label>
      <input type="checkbox" id="javascript" value="javascript" v-model="formValues.setSkills">
      <label for="javascript">Javascript</label>
    </div>

    <div>
      <label>Years of war</label>
      <input type="radio" id="0-2" value="0-2" v-model="formValues.yearsOfExperience">
      <label for="0-2">0-2</label>
      <input type="radio" id="3-5" value="3-5" v-model="formValues.yearsOfExperience">
      <label for="3-5">3-5</label>
      <input type="radio" id=">6" value=">6" v-model="formValues.yearsOfExperience">
      <label for=">6">>6</label>
    </div>
    
    <div>
      <label for="age">Age</label>
      <input @keyup.enter="submitForm2" type="number" id="age" v-model.number="formValues.age">
    </div>

    <!--<div>
      <button>Submit crack!</button>
    </div>-->

    <!--   OJO   !!!!!!!-->
    <!-- Hay que investigar sobre todos los modifiers, mouse modifiers,
    keyboard modifiers, @keyup es el modificador para teclado creo
    hay que investigar cual es el modificador para raton-->

  </form>

</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      formValues:{
        name: '',
        profileSummary: '',
        country: '',
        platillo: '',
        remoteWork: false,
        estupidez: 'yes',
        setSkills: [],
        yearsOfExperience: '',
        age: null
      }
    }
  },
  methods: {
    submitForm(event){
      event.preventDefault();
      console.log('Form values', this.formValues)
    },
    submitForm2(){
      console.log('Form values', this.formValues)
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
