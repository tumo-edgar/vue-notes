<template>
  <div class="main">
    <div class="header">
      <h1 class="title">Note App</h1>
      <Search @onSearch="onSearch" />
    </div>

    <div class="notes">
      <Card v-for="(item, index) in fitler" :title="item.title" :content="item.content" :date="item.date"
        @delete="deleteNote(index)" @click="edit(index, item)" />
    </div>

    <AddButton @click="toggleOpen" />

    <NoteForm v-if="isOpen" @onClose="toggleOpen" @onSave="addNote" :note="editable" />
  </div>
</template>

<script setup>
import { ref, onMounted, computed } from 'vue';
import AddButton from './components/AddButton.vue';
import Card from './components/Card.vue';
import NoteForm from './components/NoteForm.vue';
import Search from './components/Search.vue';

let isOpen = ref(false);
let notes = ref([])
let text = ref('')
let editable = ref(null)
let editableIndex = ref(null)

function toggleOpen() {
  if(isOpen.value){
    isOpen.value = false
    editable.value = null
    editableIndex.value = null
  }else {
    isOpen.value = true
  }
}

function addNote(title, content) {
  let today = new Date();

  const obj = {
    title: title,
    content: content,
    date: today.toLocaleString()
  }

  if(editableIndex.value !== null){
    notes.value = notes.value.map((item, index)=>{
      if(editableIndex.value === index){
        return obj
      } else {
        return item
      }
    })
  } else {
    notes.value.push(obj)
  }

  isOpen.value = false
  editable.value = null
  editableIndex.value = null
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

function onSearch(t){
  text.value = t
}

let fitler = computed(()=>notes.value.filter(
  (note) => note.title.includes(text.value)
))



function edit(index, note){
  editableIndex.value = index
  editable.value = note

  isOpen.value = true
}
 
</script>

<style scoped>
.main {
  width: 100%;
  min-height: 100vh;
  background: linear-gradient(128deg, rgba(135, 246, 180, 0.84) 12.75%, rgba(50, 180, 187, 0.67) 83.4%);
  padding: 32px;
}

.title {
  text-align: center;
  font-size: 42px;
  font-weight: 900;
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