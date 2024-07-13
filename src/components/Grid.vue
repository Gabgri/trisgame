<template>
    <!--Grid-->
    <div class="mx-auto mt-10 max-w-md"> 
        <!--Rows-->
        <div class="grid grid-cols-3"> 
            <div>{{ input }}</div>
            <div class="border-x-2 border-gray-700">
                {{ input }}</div>
            <img src="../assets/oTris.svg" alt="logo">
            <!-- <div>{{ input }}</div> -->
        </div>
        <div class="grid grid-cols-3"> 
            <div class="border-y-2 border-gray-700">
                {{ input }}</div>
            <div class="border-2 border-gray-700">
                {{ input }}</div>
            <div class="border-y-2 border-gray-700">
                <img src="../assets/oTris.svg" alt="logo"></div>
        </div>
        <div class="grid grid-cols-3"> 
            <div>{{ input }}</div>
            <div class="border-x-2 border-gray-700">
                {{ input }}</div>
            <!-- <div>{{ input }}</div> -->
            <img src="../assets/oTris.svg" alt="logo">
        </div>
    </div>


    <!-- <div class="mx-10 mt-20 "> 

        <div class="flex justify-center"> 
            <div>{{ input }}</div>
            <div class="border-x-2 border-gray-700"><p>Riga 1</p></div>
            <div><p>Riga 1</p></div>
        </div>
        <div class="flex justify-center"> 
            <div class="border-y-2 border-gray-700"><p>Riga 2</p></div>
            <div class="border-2 border-gray-700"><p>Riga 2</p></div>
            <div class="border-y-2 border-gray-700"><p>Riga 2</p></div>
        </div>
        <div class="flex justify-center"> 
            <div><p>Riga 3</p></div>
            <div class="border-x-2 border-gray-700"><p>Riga 3</p></div>
            <div><p>Riga 3</p></div>
        </div>
    </div>  -->
</template>

<script setup>
  const input = false;
  const output = 'x';

</script>