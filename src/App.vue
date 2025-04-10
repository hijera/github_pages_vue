<script setup>
import { ref } from 'vue'

const count = ref(0)
const message = ref('Привет, GitHub Pages!')
</script>

<template>
  <div class="container">
    <h1>{{ message }}</h1>
    <div class="card">
      <button type="button" @click="count++">Счётчик: {{ count }}</button>
      <p>
        Это простое Vue приложение для GitHub Pages
      </p>
    </div>
    <p class="info">
      Нажимайте кнопку, чтобы увеличить счётчик
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

.card {
  background-color: #f8f8f8;
  border-radius: 8px;
  padding: 2rem;
  margin-bottom: 2rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

button {
  background-color: #42b883;
  color: white;
  border: none;
  padding: 0.75rem 1.5rem;
  border-radius: 4px;
  font-size: 1rem;
  cursor: pointer;
  margin-bottom: 1rem;
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
