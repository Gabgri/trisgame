<template>
    <!--Grid-->
    <div id="grid" class="grid grid-cols-3 sm:max-w-md md:max-w-lg lg:max-w-xl"> 

        <!--Rows-->
        <Box v-for="i in 9" :key="i" 
        @click.once="handler" :trueOrfalse="state"
        class="h-32" :class="getStyle(i)"/>
    
    </div>
</template>

<script setup>
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
  console.log(state.value);
  state.value = !state.value;
}
</script>