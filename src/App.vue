<template>
  <h1 class="mt-10 mb-4 text-4xl font-bold">TrisGame</h1>

  <div class="flex justify-center my-10">
    <button v-show="!isStarted" @click="startGame" 
    class="self-center text-xl font-bold bg-slate-200 text-gray-800 rounded border-b-2 border-blue-500 hover:border-blue-600 hover:bg-blue-500 hover:text-white shadow-md py-2 w-60">
    Start Your Game!</button>

    <button v-show="isStarted" @click="startGame"
    class="text-xl font-bold bg-slate-200 text-gray-800 rounded border-b-2 border-blue-500 hover:border-blue-600 hover:bg-blue-500 hover:text-white shadow-md py-2 w-60">
    Reset</button>
  </div>

  <Grid v-if="isStarted" class="mx-auto"/>
</template>

<script setup>
import Grid from "./components/Grid.vue";
import { ref } from "vue";

  const isStarted = ref(false);
  function startGame() {
    isStarted.value = !isStarted.value;
  }
</script>