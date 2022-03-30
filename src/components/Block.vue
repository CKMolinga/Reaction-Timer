<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Click me</div>
</template>

<script>
export default {
props: ['delay'],
data() {
  return {
    showBlock: false,
    timer: null,
    reactionTime: 0
  }
},
mounted () {
  setTimeout(() => {
    this.showBlock = true
    this.startTimer()
    console.log(this.delay)
  }, this.delay)
},
methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10
      }, 10)
    }, 
    stopTimer() {
      clearInterval(this.timer)
        this.$emit('reaction', this.reactionTime)
    }
}
}
</script>

<style>
.block {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 400px;
  text-align: center;
  background: #0faf87;
  color: #fff;
  margin: 40px auto;
  padding: 100px 0;
  border-radius: 20px;
  cursor: pointer;
}

</style>