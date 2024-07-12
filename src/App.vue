<template>
  <h1 class="text-3xl font-bold">TrisGame</h1>
  <button class="bg-slate-200 text-gray-800 font-bold rounded border-b-2 border-blue-500 hover:border-blue-600 hover:bg-blue-500 hover:text-white shadow-md py-2 px-6 inline-flex items-center"
  v-show="!isStarted" @click="startGame">Start Your Game!</button>
  <button class="bg-slate-200 text-gray-800 font-bold rounded border-b-2 border-blue-500 hover:border-blue-600 hover:bg-blue-500 hover:text-white shadow-md py-2 px-6 inline-flex items-center"
  v-show="isStarted">Reset</button>
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
