<template>
  <h1>TrisGame</h1>
  <button v-show="!isStarted" @click="startGame">Start Your Game!</button>
  <button v-show="isStarted">Reset</button>
  <p>{{ input }} has won the Game</p>
  <Grid v-if="isStarted"/>
</template>

<script>
import Grid from './components/Grid.vue';

export default {
  name: 'TrisGame',
  components: { Grid },
  data() {
    return {
      isStarted: false
    }
  },
  methods: {
    startGame() {
      this.isStarted = !this.isStarted;
    },
    showWinner() {
      
    }
  },
  computed: {
    reset () {
    }
  },
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
