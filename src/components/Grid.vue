<template>
    <!--Grid-->
    <div id="grid" class="grid grid-cols-3 sm:max-w-md md:max-w-lg lg:max-w-xl
    "> 

        <!--Rows-->
        <Box v-for="i in 9" :key="i" 
        @click.once="handler" :trueOrfalse="state"
        class="h-32" :class="getStyle(i)"></Box>
    

        <!-- <Box @click.once="handler"
        :trueOrfalse="state" class="h-32"/>
        <Box @click.once="handler"
        :trueOrfalse="state"
        class="border-x-2 border-gray-700"/>
        <Box @click.once="handler"
        :trueOrfalse="state"/>

        <Box @click.once="handler"
        :trueOrfalse="state" 
        class="border-y-2 border-gray-700 h-32"/>
        <Box @click.once="handler"
        :trueOrfalse="state"
        class="border-2 border-gray-700"/>
        <Box @click.once="handler"
        :trueOrfalse="state"
        class="border-y-2 border-gray-700"/>

        <Box @click.once="handler"
        :trueOrfalse="state" class="h-32"/>
        <Box @click.once="handler"
        :trueOrfalse="state"
        class="border-x-2 border-gray-700"/>
        <Box @click.once="handler"
        :trueOrfalse="state"/> -->

    </div>
</template>

<script setup>
import { Result } from "postcss";
import Box from "./Box.vue";
import { reactive, ref } from "vue";

const state = ref(true);

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

function handler() {
  state.value = !state.value;
}
</script>

<!--
Orizzontali: [1, 2, 3], [4, 5, 6], [7, 8, 9]
Verticali: [1, 4, 7], [2, 5, 8], [3, 6, 9]
Diagonali: [1, 5, 9], [3, 5, 7]
-->