<template>
    <!--Grid-->
    <div @click="handler" id="grid" class="grid grid-cols-3"> 

        <!--Rows-->
        <Box :trueOrfalse="state"/>
        <Box :trueOrfalse="state"
        class="border-x-2 border-gray-700"/>
        <Box :trueOrfalse="state"/>

        <Box :trueOrfalse="state"
        class="border-y-2 border-gray-700"/>
        <Box :trueOrfalse="state"
        class="border-2 border-gray-700"/>
        <Box :trueOrfalse="state"
        class="border-y-2 border-gray-700"/>

        <Box :trueOrfalse="state"/>
        <Box :trueOrfalse="state"
        class="border-x-2 border-gray-700"/>
        <Box :trueOrfalse="state"/>

    </div>
</template>

<script setup>
import Box from "./Box.vue";
import { ref } from "vue";

const state = ref(false);

function handler() {
  state.value = !state.value;
}
</script>

<!--
Orizzontali: [1, 2, 3], [4, 5, 6], [7, 8, 9]
Verticali: [1, 4, 7], [2, 5, 8], [3, 6, 9]
Diagonali: [1, 5, 9], [3, 5, 7]
-->