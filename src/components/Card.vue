<template>
  <div class="Card">
    <h2>{{ props.title }}</h2>
    <p class="Text">
  {{ props.content }}
    </p>
    <p class="date"></p>
    {{ props.date }}
  </div>
  </template>


<script setup> 
import {defineProps} from 'vue';
let props = defineProps(['title','content', 'date'])


 </script>

<style scoped>
.Card{
background: linear-gradient(114.43deg, #00aeffbc 4%, #ffffff1a 100%);

font-size:18px;
border-radius: 10px;
padding: 20px;
width: 320px;
height: 208px;
}
.Text {
display: -webkit-box;
-webkit-box-orient: vertical;
-webkit-line-clamp: 3;
overflow: hidden;
height: 87px;
}
.date{
  text-align: right;
  margin-top: 10px;
}

</style>  