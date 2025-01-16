<template>
    <div class="container">
      <div id="app" class="calculator">
        <h1>Calculadora Aritmética</h1>
        <div class="form-group">
          <label for="num1">Valor 1:</label>
          <input type="number" id="num1" v-model.number="num1" />
        </div>
    
        <div class="form-group">
          <label for="num2">Valor 2:</label>
          <input type="number" id="num2" v-model.number="num2" />
        </div>
    
        <div class="form-group">
          <label for="operation">Operação:</label>
          <select id="operation" v-model="operation">
            <option value="add">Soma</option>
            <option value="subtract">Subtração</option>
            <option value="multiply">Multiplicação</option>
            <option value="divide">Divisão</option>
          </select>
        </div>
    
        <div class="result">
          <h2>Valor final: {{ result }}</h2>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: 'add',
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case 'add':
          return this.num1 + this.num2;
        case 'subtract':
          return this.num1 - this.num2;
        case 'multiply':
          return this.num1 * this.num2;
        case 'divide':
          return this.num2 !== 0 ? (this.num1 / this.num2).toFixed(2) : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    },
  },
};
</script>

<style scoped>

.container {
  display: grid;
  justify-content: center;
  padding: 80px;
}


.calculator {
  max-width: 400px;
  margin: 100px auto;
  padding: 40px;
  border: 1px solid #ccc;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  font-family: "Roboto", serif;
  background-color: rgb(216, 217, 219);
  text-align: center;
}

.form-group {
  margin-bottom: 15px;
}

label {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
}

input,
select {
  width: auto;
  padding: 12px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 8px;
  cursor: pointer;
}

.result {
  margin-top: 40px;
  text-align: center;
}
</style>

