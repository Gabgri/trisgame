<template>
  <div>
  <h1 class="mb-10 text-4xl font-bold">TrisGame</h1>

  <button v-show="!isStarted" @click="startGame" 
  class="text-xl font-bold bg-slate-200 text-gray-800 rounded border-b-2 border-blue-500 hover:border-blue-600 hover:bg-blue-500 hover:text-white shadow-md py-2 px-6">
  Start Your Game!</button>

  <button v-show="isStarted" @click="startGame"
  class="text-xl font-bold bg-slate-200 text-gray-800 rounded border-b-2 border-blue-500 hover:border-blue-600 hover:bg-blue-500 hover:text-white shadow-md py-2 px-6">
  Reset</button>

  <!-- <p> has won the Game</p> -->
  <Grid v-if="isStarted" />
</div>
</template>

<script setup>
import Grid from "./components/Grid.vue";
import { ref } from "vue";

  const isStarted = ref(false);
  function startGame() {
    isStarted.value = !isStarted.value;
  }
</script>

<!--
Orizzontali: [1, 2, 3], [4, 5, 6], [7, 8, 9]
Verticali: [1, 4, 7], [2, 5, 8], [3, 6, 9]
Diagonali: [1, 5, 9], [3, 5, 7]
-->