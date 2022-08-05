<template>
  <div>
    <img class="imc-logo" src="./assets/imc.png" alt="Imc logo">
    <h1>Calcule seu IMC (Índice de Massa Corporal)</h1>

    <div class="weight">
      <label for="weight">Peso (kg): </label>
      <input id="weight" type="number" v-model="weight">
    </div>

    <div class="height">
      <label for="height">Altura (cm):</label>
      <input id="height" type="number" v-model="height">
    </div>

    <button class="btn-calculation" @click="calculateImc">Calcular</button>

    <div class="result">
      <p class="imc-result"></p>
      <p class="body-type">Peso normal</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      weight: 0,
      height: 0
    }
  },
  methods: {
    calculateImc: function () {

    }
  }
}


</script>

<style>
#app {
  display: block;
  margin: 60px auto;
  width: fit-content;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.imc-logo {
  width: 200px;
}

.weight,
.height {
  padding: 1em;
}

input {
  padding: .5em;
  margin-left: .5em;
  outline: none;
}

button {
  margin-top: 2em;
  padding: .5em 2em;
  border: 2px solid black;
  background-color: aliceblue;
  color: black;
  text-transform: uppercase;
}

button:hover {
  background-color: black;
  color: white;
}

.result {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin-top: 40px;
  background-color: rgb(149, 216, 199);
}

.imc-result {
  font-size: 2em;
}

.body-type {
  font-size: 2em;
}
</style>
