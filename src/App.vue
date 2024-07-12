<template>
  <h1 class="text-3xl font-bold">TrisGame</h1>
  <button v-show="!isStarted" @click="startGame">Start Your Game!</button>
  <button v-show="isStarted">Reset</button>
  <p>{{ input }} has won the Game</p>
  <Grid v-if="isStarted" />
</template>

<script setup>
import Grid from "./components/Grid.vue";
import { ref } from "vue";

  const isStarted = ref(false);
  function startGame() {
    isStarted.value = !isStarted.value;
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
