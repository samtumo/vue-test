<script setup>
import { ref, onMounted, computed } from 'vue';
import AddButton from './components/AddButton.vue'
import Card from './components/Card.vue';
import NoteForm from './components/NoteForm.vue';
import Search from './components/Search.vue';

let isOpen = ref(false);

function toggleOpen() {
  if (isOpen.value === true) {
    isOpen.value = false
    editable.value = null
    editableindex.value = null

  } else {
    isOpen.value = true
  }
}
let notes = ref([])

function addNote(title, content) {
  let today = new Date();
  const obj = {
    title: title,
    content: content,
    date: today.toLocaleDateString()
  }
  if(editableindex.value !== null){
   notes.value = notes.value.map((item, index)=>{
    if(editableindex.value === index){
      return obj
      
    

   }else{
    return item
   }
  })
  } else {
  notes.value.push(obj)
  }
  localStorage.setItem('notes', JSON.stringify(notes.value))
}
function deleteNote(index) {
  notes.value.splice(index, 1)
  localStorage.setItem('notes', JSON.stringify(notes.value))
}
onMounted(() => {
  let savedNotes = localStorage.getItem('notes')
  if (savedNotes) {
    notes.value = JSON.parse(savedNotes)
  }
})

let text = ref('')


function onSearch(t){
  text.value=t

}
let filter = computed(()=>notes.value.filter(
  (note) => note.title.includes(text.value)

))

let editable = ref(null)
let editableindex = ref(null)


function edit(index, note){
  editableindex.value=index
editable.value = note
isOpen.value = true
}

</script>

<template>
  <div class="main">
    <div class="header">
      <h1 class="title">Note App</h1>
      <Search @onSearch="onSearch"/>
    </div>
    <AddButton @click="toggleOpen" />
    <NoteForm v-if="isOpen" @onClose="toggleOpen" @onSave="addNote" :note="editable" />
    <div class="notes">
      <Card v-for="(item, index) in filter " :title="item.title" :content="item.content" :date="item.date"
        @delete="deleteNote(index)" @click="edit(index, item)"/>

    </div>

  </div>
</template>

<style scoped>
.main {
  width: 100%;
  min-height: 100vh;
  background: linear-gradient(128deg, rgba(0, 191, 255, 0.84) 12.75%, rgba(255, 255, 255, 0.67) 83.4%);
  font-size: 40px;
  font-weight: 500;

}

.title {
  text-align: center;
  padding: 20px;
}

.notes {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.header {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 32px;
}
</style>