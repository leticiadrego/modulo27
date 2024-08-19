<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: '+',
    };
  },
  computed: {
    calculate() {
      let result;
      switch (this.operation) {
        case '+':
          result = this.num1 + this.num2;
          break;
        case '-':
          result = this.num1 - this.num2;
          break;
        case '*':
          result = this.num1 * this.num2;
          break;
        case '/':
          result = this.num2 !== 0 ? this.num1 / this.num2 : 'Erro: Divisão por zero';
          break;
        default:
          result = 'Operação inválida';
      }
      return result;
    },
  },
};
</script>

<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div>
      <label for="num1">Número 1:</label>
      <input type="number" v-model.number="num1" id="num1" />
    </div>
    <div>
      <label for="num2">Número 2:</label>
      <input type="number" v-model.number="num2" id="num2" />
    </div>
    <div>
      <label for="operation">Operação:</label>
      <select v-model="operation" id="operation">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
    </div>
    <div>
      <h2>Resultado: {{ calculate }}</h2>
    </div>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #0D33B3;
  margin-top: 60px;
}

label {
  display: inline-block;
  width: 100px;
  text-align: right;
  margin-right: 10px;
}

input,
select {
  margin-bottom: 10px;
}

h2 {
  margin-top: 20px;
}
</style>
