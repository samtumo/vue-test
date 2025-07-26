<template>
<div class="search">
<input @keydown.enter="$emit('onSearch',text)" type="search" v-model="text"/>
<button @click="$emit('onSearch',text)">
<i class="fa-solid fa-magnifying-glass"></i>  
</button>
</div>

</template>

<script setup>
import {ref} from 'vue';

let text = ref('')

</script>

<style scoped>
.search{
width: 350px;
height: 40px;
display:flex;
}
input{
    flex:1;
    border-radius: 4px;
    background: linear-gradient(128deg, rgba(0, 191, 255, 0.84) 12.75%, rgba(255, 255, 255, 0.67) 83.4%);
}
button {
    width: 40px;
    height: 40px;
}

</style>