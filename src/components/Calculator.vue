<template>
  <div class="calculator">
    <div class="display">{{ currentInput || '0' }}</div>
    <div class="buttons">
      <button @click="clear">C</button>
      <button @click="input('.')">.</button>
      <button @click="input('/')">/</button>

      <button @click="input('+')">+</button>
      <button @click="input('7')">7</button>
      <button @click="input('8')">8</button>
      <button @click="input('9')">9</button>

      <button @click="input('-')">-</button>
      <button @click="input('4')">4</button>
      <button @click="input('5')">5</button>
      <button @click="input('6')">6</button>

      <button @click="input('*')">*</button>
      <button @click="input('1')">1</button>
      <button @click="input('2')">2</button>
      <button @click="input('3')">3</button>
      <button @click="calculate">=</button>
      <button @click="input('0')">0</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentInput: '',
    };
  },
  methods: {
    input(value) {
      this.currentInput += value;
    },
    clear() {
      this.currentInput = '';
    },
    calculate() {
      try {
        this.currentInput = eval(this.currentInput).toString();
      } catch {
        this.currentInput = 'Erro';
      }
    },
  },
};
</script>

<style>
.calculator {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
  border: 2px solid #ccc;
  border-radius: 10px;
  background-color: #f9f9f9;
  box-shadow: 1px 1px 10px 1px rgba(0, 0, 0, 0.2);
}

.display {
  font-weight: bold;
  width: 90%;
  margin-bottom: 10px;
  padding: 8px;
  border: 1px solid #ddd;
  background: #fff;
  font-size: 1.5rem;
  text-align: right;
  border-radius: 5px;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 5px;
}

button {
  padding: 10px;
  font-size: 1.2rem;
  background: #e0e0e0;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background 0.2s;
}

button:hover {
  background: #d4d4d4;
}
</style>
