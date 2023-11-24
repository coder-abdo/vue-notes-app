<script setup>
import { ref } from "vue";
import Notes from "./components/notes.vue";
import Header from "./components/header.vue";
import Modal from "./components/modal.vue";
const showModal = ref(false);
const notes = ref([]);
const note = ref("");
const showNoteModal = () => {
  showModal.value = true;
};
const closeNoteModal = () => {
  showModal.value = false;
};
const addNote = () => {
  notes.value.push({
    text: note.value,
    date: new Date().toLocaleString(),
  });
  note.value = "";
  showModal.value = false;
};
</script>

<template>
  <main>
    <Modal
      :showModal="showModal"
      :note="note"
      @update:note="note = $event"
      :closeNoteModal="closeNoteModal"
     :addNote="addNote"
    />
    <div class="container">
      <Header :showNoteModal="showNoteModal" />
      <Notes :notes="notes" />
    </div>
  </main>
</template>

<style scoped>
main {
  background-color: rgb(241 245 249);
  min-height: 100vh;
  padding: 1rem;
}
.container {
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
  position: relative;
}

button {
  background-color: rgb(0 0 0);
  border: none;
  color: rgb(255 255 255);
  cursor: pointer;
  height: 2.5rem;
  font-size: 1.5rem;
}
</style>
