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

    <button class="btn-calculation" @click="calculateImc(); newBodyType();">Calcular</button>

    <div class="result">
      <p class="imc-result">{{ imc }}</p>
      <p class="body-type">{{ bodyType }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      weight: 0,
      height: 0,
      imc: 0,
      bodyType: 'Insira seus dados'
    }
  },
  methods: {
    calculateImc: function () {
      return this.imc = (this.weight / (this.height * this.height)).toFixed(2);
    },
    newBodyType: function () {
      if (this.imc >= 16 && this.imc <= 16.9 || this.imc < 16) return this.bodyType = `Muito abaixo do peso.`
      if (this.imc >= 17 && this.imc <= 18.4) return this.bodyType = `Abaixo do peso.`
      if (this.imc >= 18.5 && this.imc <= 24.9) return this.bodyType = `Peso normal.`
      if (this.imc >= 25 && this.imc <= 29.9) return this.bodyType = `Acima do peso.`
      if (this.imc >= 30 && this.imc <= 34.9) return this.bodyType = `Obesidade grau I.`
      if (this.imc >= 35 && this.imc <= 40) return this.bodyType = `Obesidade grau II.`
      if (this.imc > 40) return this.bodyType = `Obesidade grau III.`
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
