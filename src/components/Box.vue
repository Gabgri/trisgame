<template>
<span @click="handler">{{ output }}</span> 
<!-- @click="handler" -->
</template>

<script setup>
import { ref } from "vue";

const props = defineProps(['trueOrfalse'])
const output = ref('');

function handler() {
    if (props.trueOrfalse) {
        output.value = 'X';
    } else {
        output.value = 'O';
    }
}

</script>