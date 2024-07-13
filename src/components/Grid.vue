<template>
    <!--Grid-->
    <div id="grid" class="mx-auto mt-10 max-w-md"> 
        <!--Rows-->
        <div class="grid grid-cols-3"> 
            <Box />
            <Box class="border-x-2 border-gray-700" />
            <Box />
        </div>
        <div class="grid grid-cols-3"> 
            <Box class="border-y-2 border-gray-700"/>
            <Box class="border-2 border-gray-700"/>
            <Box class="border-y-2 border-gray-700"/>
        </div>
        <div class="grid grid-cols-3"> 
            <Box />
            <Box class="border-x-2 border-gray-700"/>
            <Box />
        </div>
    </div>

    <Box />
</template>

<script setup>
import Box from "./Box.vue";


</script>

<!--
Orizzontali: [1, 2, 3], [4, 5, 6], [7, 8, 9]
Verticali: [1, 4, 7], [2, 5, 8], [3, 6, 9]
Diagonali: [1, 5, 9], [3, 5, 7]
-->