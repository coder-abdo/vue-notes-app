<script>
export default {
  name: "Modal",
  props: {
    showModal: Boolean,
    note: String,
    closeNoteModal: Function,
    addNote: Function,
  },
};
</script>
<template>
  <div v-if="showModal" class="overlay">
    <div class="modal">
      <h2>Create Note</h2>
      <textarea
        :value="note"
        @input="$emit('update:note', $event.target.value)"
        rows="10"
      ></textarea>
      <button class="close-btn" @click="closeNoteModal">x</button>
      <button class="save-btn" @click="addNote">Save</button>
    </div>
  </div>
</template>
<style scoped>
.overlay {
  position: fixed;
  inset: 0;
  background-color: rgba(0, 0, 0, 0.5);
  width: 100%;
  min-height: 100vh;
  z-index: 100;
}
.modal {
  background-color: rgb(255, 255, 255);
  width: 50%;
  margin: 0 auto;
  margin-top: 10rem;
  padding: 1rem;
  border-radius: 0.5rem;
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 2rem;
}
.modal h2 {
  margin: 0;
  text-align: center;
  text-transform: capitalize;
}
.modal textarea {
  width: 100%;
  border: 1px solid #333;
  border-radius: 0.5rem;
  padding: 1rem;
  margin-bottom: 1rem;
  resize: none;
  font-size: 1rem;
  transition-property: border-color;
  transition-duration: 0.3s;
  transition-timing-function: ease-in-out;
}
.modal .close-btn {
  position: absolute;
  top: 1rem;
  right: 1rem;
  background-color: rgb(0, 0, 0);
  color: rgb(255, 255, 255);
  border: none;
  border-radius: 50%;
  width: 2.5rem;
  height: 2.5rem;
  font-size: 1.5rem;
  cursor: pointer;
}
.modal textarea:focus {
  outline: none;
  border: 1px solid #89b6ff;
}
.modal .save-btn {
  background-color: rgb(0, 0, 0);
  color: rgb(255, 255, 255);
  border: 1px solid #333;
  border-radius: 0.5rem;
  width: 100%;
  height: 2.5rem;
  font-size: 1.5rem;
  cursor: pointer;
  transition-property: background-color, color;
  transition-duration: 0.3s;
  transition-timing-function: ease-in-out;
}
.modal .save-btn:hover {
  background-color: transparent;
  color: #333;
}
</style>
