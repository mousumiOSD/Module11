<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>
<template>
  <div>
    <h2>Calculator</h2>
    <form @submit.prevent="calculate">
      <label for="num1">Number 1:</label>
      <input v-model="num1" type="number" required />

      <label for="operator">Operator:</label>
      <select v-model="operator" required>
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>

      <label for="num2">Number 2:</label>
      <input v-model="num2" type="number" required />

      <button type="submit">Calculate</button>
    </form>

    <div v-if="result !== null">
      <p>Result: {{ result }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: "",
      num2: "",
      operator: "+",
      result: null,
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case "+":
          this.result = parseFloat(this.num1) + parseFloat(this.num2);
          break;
        case "-":
          this.result = parseFloat(this.num1) - parseFloat(this.num2);
          break;
        case "*":
          this.result = parseFloat(this.num1) * parseFloat(this.num2);
          break;
        case "/":
          this.result = parseFloat(this.num1) / parseFloat(this.num2);
          break;
      }
    },
  },
};
</script>
