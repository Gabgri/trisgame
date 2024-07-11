<template>
    <!--Grid-->
    <div> 
        <p>Sono dentro il template "grid"</p>
        <!--Rows-->
        <div> 
            <p>Riga 1</p>
            <Box />
            <Box />
            <Box />
        </div>
        <div> 
            <p>Riga 2</p>
            <Box />
            <Box />
            <Box />
        </div>
        <div> 
            <p>Riga 3</p>
            <Box />
            <Box />
            <Box />
        </div>
    </div>
</template>

<script>
import Box from './Box.vue';
export default { 
    components: { Box }
}
</script>