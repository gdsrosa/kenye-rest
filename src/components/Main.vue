<template>
  <div class="main">
    <h3>Kenye West Sentences</h3>
    <button @click="handleQuote">Generate Quote</button>

    <p v-if="quote">{{ quote }}</p>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Main',
  data: () => ({
    quote: null
  }),
  methods: {
    async handleQuote() {
      const { data } = await axios.get('https://api.kanye.rest/')
      this.quote = data.quote
    }
  }
}
</script>

<style scoped lang="scss">
.main {
  display: flex;
  flex-direction: column;
  text-align: center;
  justify-content: center;
}

h3 {
  font-size: 2em;
}

button {
  background-color: tomato;
  border-radius: 5px;
  border: 1px solid tomato;
  color: black;
  cursor: pointer;
  font-size: 1.5em;
  margin: 25px auto;
  max-width: 300px;
  outline: none;
  padding: 10px;
  width: 100%;
}
</style>
