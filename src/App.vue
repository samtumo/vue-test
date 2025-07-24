<script setup>
import {ref} from 'vue';
import AddButton from './components/AddButton.vue'
import Card from './components/Card.vue';
import NoteForm from './components/NoteForm.vue';

let isOpen = ref(false);

function toggleOpen() {
if (isOpen.value === true) {
    isOpen.value = false
    
}else {
  isOpen.value = true
}
}


 </script>

<template>
<div class="main">
  <h1 class="title">Note App</h1>
<AddButton @click="toggleOpen"/>
<NoteForm v-if="isOpen" @onClose="toggleOpen"/>
<div class="notes">
  <Card title="My Text"/>
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
padding: 20px;
}
.notes{
  display: flex;
  
}
</style>
  