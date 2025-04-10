<script setup>
import { ref, computed } from 'vue'

const message = ref('Привет, Аня!')
const num1 = ref('')
const num2 = ref('')
const operation = ref('+')

const result = computed(() => {
  const a = parseFloat(num1.value) || 0
  const b = parseFloat(num2.value) || 0
  
  switch(operation.value) {
    case '+': return a + b
    case '-': return a - b
    case '*': return a * b
    case '/': return b !== 0 ? a / b : 'Ошибка: деление на ноль'
    default: return 0
  }
})

const clearInputs = () => {
  num1.value = ''
  num2.value = ''
  operation.value = '+'
}
</script>

<template>
  <div class="container">
    <h1>{{ message }}</h1>
    <div class="card">
      <h2>Калькулятор</h2>
      
      <div class="calculator">
        <div class="input-group">
          <input type="number" v-model="num1" placeholder="Введите число">
          
          <select v-model="operation">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">×</option>
            <option value="/">/</option>
          </select>
          
          <input type="number" v-model="num2" placeholder="Введите число">
        </div>
        
        <div class="result">
          <h3>Результат: {{ result }}</h3>
        </div>
        
        <button @click="clearInputs">Очистить</button>
      </div>
    </div>
    
    <p class="info">
      Введите числа и выберите операцию для вычисления
    </p>
  </div>
</template>

<style scoped>
.container {
  font-family: Arial, sans-serif;
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
}

h1 {
  color: #42b883;
  margin-bottom: 2rem;
}

h2 {
  color: #444;
  margin-bottom: 1.5rem;
}

.card {
  background-color: #f8f8f8;
  border-radius: 8px;
  padding: 2rem;
  margin-bottom: 2rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
}

.input-group {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

input, select {
  padding: 0.75rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 1rem;
}

input {
  width: 120px;
}

select {
  width: 60px;
  text-align: center;
}

.result {
  background-color: #e9f7f2;
  padding: 1rem;
  border-radius: 4px;
  margin-bottom: 1rem;
  min-width: 300px;
}

button {
  background-color: #42b883;
  color: white;
  border: none;
  padding: 0.75rem 1.5rem;
  border-radius: 4px;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #369f6b;
}

.info {
  color: #666;
  font-size: 0.9rem;
}
</style>
