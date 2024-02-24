<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>
  <div>
    <h2>Quote Display</h2>
    <button @click="fetchQuote">Fetch Quote</button>

    <div v-if="quote">
      <p>ID: {{ quote.id }}</p>
      <p>Quote: {{ quote.quote }}</p>
      <p>Anime: {{ quote.anime }}</p>
      <p>Character: {{ quote.character }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quote: null,
    };
  },
  methods: {
    fetchQuote() {
      fetch("https://animechan.xyz/api/random")
        .then((response) => response.json())
        .then((data) => {
          this.quote = data;
        })
        .catch((error) => {
          console.error("Error fetching quote:", error);
        });
    },
  },
};
</script>


