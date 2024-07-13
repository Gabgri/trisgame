<template>
<span @click="handler">{{ output }}</span> 
</template>

<script setup>
import { ref } from "vue";
  let input = false;
  const output = ref('-');

  function handler() {
    console.log("clicked");
    if (input) {
      output.value = "X";
    } else {
      output.value = "O";
    }
    input = !input;
    console.log(input);
  }
</script>