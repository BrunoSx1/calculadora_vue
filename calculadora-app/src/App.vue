<script>
export default {
  name: 'App',
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: '+',
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case '+':
          return this.number1 + this.number2;
        case '-':
          return this.number1 - this.number2;
        case '*':
          return this.number1 * this.number2;
        case '/':
          return this.number1 / this.number2;
        default:
          return 0;
      }
    },
  },
  methods: {
    calculate() {
      // Não faz nada, já que o cálculo é feito por meio do computed
    },
  },
};
</script>

<template>
  <div>
    <h1>Calculadora</h1>
    <div>
      <label for="number1">Número 1:</label>
      <input id="number1" type="number" v-model="number1" @input="calculate">
    </div>
    <div>
      <label for="number2">Número 2:</label>
      <input id="number2" type="number" v-model="number2" @input="calculate">
    </div>
    <div>
      <label for="operation">Operação:</label>
      <select id="operation" v-model="operation" @change="calculate">
        <option value="+">Adição</option>
        <option value="-">Subtração</option>
        <option value="*">Multiplicação</option>
        <option value="/">Divisão</option>
      </select>
    </div>
    <div>
      <label>Resultado:</label>
      <input type="text" :value="result" disabled>
    </div>
  </div>
</template>


<style scoped>
</style>
