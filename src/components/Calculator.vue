<template>
    <div class="calculator container">
      <div class="row justify-content-center align-items-center">
        <h1>Calculadora Vue.JS </h1>
        <br>
        <hr>
        <br>
        <div class="col-md-3">
          <input v-model.number="firstNumber" type="number" class="form-control" placeholder="Primeiro Número" />
        </div>
        <div class="col-md-2">
          <select v-model="operation" class="custom-select">
            <option>+</option>
            <option>-</option>
            <option>*</option>
            <option>/</option>
          </select>
        </div>
        <div class="col-md-3">
          <input v-model.number="secondNumber" type="number" class="form-control" placeholder="Segundo Número" />
        </div>
        <div class="col-md-3 mt-3">
          <h2 class="text-center">Resultado: {{ result }}</h2>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        firstNumber: null,
        secondNumber: null,
        operation: '+'
      }
    },
    computed: {
      result() {
        switch (this.operation) {
          case '+':
            return this.firstNumber + this.secondNumber;
          case '-':
            return this.firstNumber - this.secondNumber;
          case '*':
            return this.firstNumber * this.secondNumber;
          case '/':
            if (this.secondNumber === 0) {
              return 'Error: Division by zero';
            } else {
              return this.firstNumber / this.secondNumber;
            }
          default:
            return 'Invalid operation';
        }
      }
    }
  }
  </script>
  
  <style scoped>
 
  .calculator {
    margin-top: 50px;
   
  }

  .custom-select {  
  color: black;  
  padding: 5px;
  border-radius: 10px;
  font-size: 1.2rem; 
 }

.custom-select:focus {
  outline: none;
}

.custom-select option {
  background: white;
  color: black;
  font-size: 1.2rem;
}
  </style>