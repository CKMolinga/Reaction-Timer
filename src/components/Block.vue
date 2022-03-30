<template>
  <div class="block" v-if="showBlock">Click me</div>
</template>

<script>
export default {
props: ['delay'],
data() {
  return {
    showBlock: false,
  }
},
mounted () {
  setTimeout(() => {
    this.showBlock = true
    console.log(this.delay)
  }, this.delay)
},
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