<script>
  export default {
    data() {
      return {
        number1: 0, 
        number2: 0, 
        operation: "add", 
      };
    },
    computed: {
      result() {
        switch (this.operation) {
          case "add":
            return this.number1 + this.number2;
          case "subtract":
            return this.number1 - this.number2;
          case "multiply":
            return this.number1 * this.number2;
          case "divide":
            return this.number2 !== 0
              ? this.number1 / this.number2
              : "Erro: Divisão por zero";
          default:
            return "Operação inválida";
        }
      },
    },
  };
</script>

<template>
  <div id="app" class="container">
    <h1>Calculadora Aritmética</h1>

    <div class="calculator">
      <!-- Campo para o primeiro número -->
      <input 
        type="number" 
        v-model.number="number1" 
        placeholder="Digite o primeiro número" 
      />

      <!-- Campo para o segundo número -->
      <input 
        type="number" 
        v-model.number="number2" 
        placeholder="Digite o segundo número" 
      />

      <!-- Select para escolher a operação -->
      <select v-model="operation">
        <option value="add">Somar</option>
        <option value="subtract">Subtrair</option>
        <option value="multiply">Multiplicar</option>
        <option value="divide">Dividir</option>
      </select>

      <!-- Resultado -->
      <div class="result">
        <p>Resultado: {{ result }}</p>
      </div>
    </div>
  </div>
</template>

<style>
.container {
  max-width: 400px;
  margin: 50px auto;
  text-align: center;
  font-family: Arial, sans-serif;
}
.calculator {
  display: flex;
  flex-direction: column;
  gap: 10px;
}
input,
select {
  padding: 8px;
  font-size: 16px;
}
.result {
  margin-top: 20px;
  font-weight: bold;
  font-size: 18px;
}
</style>
