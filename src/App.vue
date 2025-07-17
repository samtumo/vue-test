<script setup>
import {ref} from 'vue';
import Card from './components/Card.vue'
let number = ref (0)
const increment = () => {number.value++

}
 </script>

<template>
<Card :number="number"/>
  <button @click = "increment">click me </button>
  
</template>

<style scoped>

h1 {color:red;}
h2 {color:blue;}
h1,h2{background-color: yellow;}

</style>
  