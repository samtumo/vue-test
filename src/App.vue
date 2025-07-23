<script setup>
import {ref} from 'vue';
import AddButton from './components/AddButton.vue'
import Card from './components/Card.vue';


 </script>

<template>
<div class="main">
  <h1 class="title">Note App</h1>
<AddButton/>
<div class="notes">
  <Card/>
  <Card/>
  <Card/>

</div>
</div>
</template>

<style scoped>
.main{
  width: 100%;
  min-height: 100vh;
  background: linear-gradient(128deg, rgba(0, 191, 255, 0.84) 12.75%, rgba(255, 255, 255, 0.67) 83.4%);
  font-size: 40px;
  font-weight: 500;
}
.title{
text-align: center;
}
.notes{
  display: flex;
  
}
</style>
  