<template>
    <!--Grid-->
    <div @click="handler" id="grid" class="mx-auto mt-10 max-w-md"> 
        <!--Rows-->
        <div class="grid grid-cols-3 h-28"> 
            <Box :trueOrfalse="state"/>
            <Box :trueOrfalse="state"
            class="border-x-2 border-gray-700" />
            <Box :trueOrfalse="state"/>
        </div>
        <div class="grid grid-cols-3 h-28"> 
            <Box :trueOrfalse="state"
            class="border-y-2 border-gray-700"/>
            <Box :trueOrfalse="state"
            class="border-2 border-gray-700"/>
            <Box :trueOrfalse="state"
            class="border-y-2 border-gray-700"/>
        </div>
        <div class="grid grid-cols-3 h-28"> 
            <Box :trueOrfalse="state"/>
            <Box :trueOrfalse="state"
            class="border-x-2 border-gray-700"/>
            <Box :trueOrfalse="state"/>
        </div>
    </div>
</template>

<script setup>
import Box from "./Box.vue";
import { ref } from "vue";

const state = ref(false);

function handler() {
  state.value = !state.value;
  console.log(state.value);
}
// function handler() {
//   clicked.value = !clicked.value;
//   console.log(clicked.value);

//   if (clicked.value) {
//     out.value = "X";
//   } else {
//     out.value = "O";
//   }
// }


//   function handler() {
//     if (input) {
//       output.value = "X";
//     } else {
//       output.value = "O";
//     }
//     input = !input;
//   }
</script>

<!--
Orizzontali: [1, 2, 3], [4, 5, 6], [7, 8, 9]
Verticali: [1, 4, 7], [2, 5, 8], [3, 6, 9]
Diagonali: [1, 5, 9], [3, 5, 7]
-->