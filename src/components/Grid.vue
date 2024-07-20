<template>
    <!--Grid-->
    <div id="grid" class="grid grid-cols-3 mx-auto sm:max-w-md md:max-w-lg lg:max-w-xl"> 

        <!--Rows-->
        <Box v-show="!result"
        v-for="i in 9" :key="i" 
        :trueOrfalse="state" 
        @click.once="handler(i)"
        class="h-32" :class="getStyle(i)"/>
    </div>

    <p v-if="result" class="text-3xl">
      Game Over! <br/>
      {{ winner }}
    </p>

</template>

<script setup>
import Box from "./Box.vue";
import { reactive, ref } from "vue";

const state = ref(true); // true = X, false = O (used to switch turns and props)
const result = ref(false); // true when winner or draw
const winner = ref(''); //return "X won" or "O won" or "Draw"

const style = reactive({
  sideX: 'border-x-2 border-gray-700',
  sideY: 'border-y-2 border-gray-700',
  bothSide: 'border-2 border-gray-700'
})

function getStyle(i) {
  if (i == 2) {
    return style.sideX;
  } else if (i == 4 | i == 6) {
    return style.sideY;
  } else if (i == 5) {
    return style.bothSide;
  } else if (i == 8) {
    return style.sideX;
  }
}

const combinations = [ [0, 0, 0],
  [1, 2, 3], [4, 5, 6], [7, 8, 9], // Horizontals
  [1, 4, 7], [2, 5, 8], [3, 6, 9], // Verticals
  [1, 5, 9], [3, 5, 7] // Diagonals
];

let clickedX = []; // place clicked X
let clickedO = []; // place clicked O

function getWinner() {
  for (let a = 0; a < combinations.length; a++) {
    let combination = combinations[a];
    if (clickedX.includes(combination[0]) && clickedX.includes(combination[1]) && clickedX.includes(combination[2])) {
      result.value = true;
      winner.value = 'X won';
      alert("X won!");
    } else if (clickedO.includes(combination[0]) && clickedO.includes(combination[1]) && clickedO.includes(combination[2])) {
      result.value = true;
      winner.value = 'O won';
      alert("O won!");
    }
  }

  if (clickedX.length + clickedO.length == 9 && !result.value) {
    result.value = true; // check if all boxes are clicked
    winner.value = 'Draw';
    alert("Draw!");
  }
}

function handler(i) {
  if (state.value) {
    clickedX.push(i);
  }
  else {
    clickedO.push(i);
  }

  state.value = !state.value;

  if (clickedX.length > 2) {
    setTimeout(() => {
      getWinner();
    }, 100); 
  }
}

</script>