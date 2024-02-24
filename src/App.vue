<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Calculator from './components/Calculator.vue'
import QuoteDisplay from './components/QuoteDisplay.vue'
</script>


<template>
  <div id="app">
    <Calculator />
    <QuoteDisplay />
  </div>
</template>

<script>
import Calculator from "./components/Calculator.vue";
import QuoteDisplay from "./components/QuoteDisplay.vue";

export default {
  components: {
    Calculator,
    QuoteDisplay,
  },
};
</script>
