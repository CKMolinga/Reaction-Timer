<template>
  <h1>Reaction Timer</h1>
  <h3>Perform the action immediately you see it 😎</h3>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @reaction="endGame" ></Block>
  <Results v-if="showResults" :score="score"></Results>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: {Block, Results},
  data () {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResults = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
    }
  }
}
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #444;
    margin-top: 60px;
  }
  
  h3 {
  text-align: center;
  }

  button {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    font-size: 1.4em;
    font-weight: bold;
    background: #0faf87;
    color: #fff;
    border: none;
    border-radius: 4px;
    padding: 10px 30px;
    cursor: pointer;
    transition: all 0.2s ease-in-out;
  }

  button[disabled] {
    opacity: 0.5;
    cursor: not-allowed;
  }
</style>
