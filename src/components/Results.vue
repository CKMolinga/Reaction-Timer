<template>
  <p>Reaction Time: {{ score }} ms</p>
  <p class="rank"> {{ rank }}</p>
</template>

<script>
export default {
props: ['score'],
data() {
    return {
        rank: null,
    }
},
mounted() {
    if (this.score < 150) {
        this.rank = 'Lord'
    } else if (this.score < 250) {
        this.rank = 'Master'
    } else if (this.score < 400) {
        this.rank = 'Pro'
    } else if (this.score < 650) {
        this.rank = 'Amatuer'
    } else {
        this.rank = 'Newbie'
    }
},
}
</script>

<style>
.rank {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    font-weight: bold;
    font-size: 1.4em;
    color: #444;
    margin-top: 60px;
}
</style>