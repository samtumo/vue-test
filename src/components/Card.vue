<template>
  <div class="Card">
    <h2>My Title</h2>
    <p class="Text">orem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the i...</p>
    <p class="date">05-07-2025 20:30</p>
  </div>
  </template>


<script setup> 
import {defineProps} from 'vue';
let props = defineProps(['number'])


 </script>

<style scoped>
.Card{
background: linear-gradient(114.43deg, #00aeffbc 4%, #ffffff1a 100%);

font-size:18px
}
</style>  