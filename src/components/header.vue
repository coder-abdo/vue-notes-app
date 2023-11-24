<script>
export default {
  name: "Header",
  props: {
    showNoteModal: Function,
  },
  showNoteModal() {
    this.$emit("showNoteModal");
  },
};
</script>
<template>
  <header>
    <h1>Notes</h1>
    <button @click="showNoteModal">+</button>
  </header>
</template>
<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
}
header button {
  background-color: rgb(0 0 0);
  border: none;
  color: rgb(255 255 255);
  cursor: pointer;
  height: 2.5rem;
  font-size: 1.5rem;
  border-radius: 50%;
  width: 2.5rem;
}
h1 {
  font-size: 2rem;
  margin: 0;
  text-align: center;
  text-transform: capitalize;
}
</style>
