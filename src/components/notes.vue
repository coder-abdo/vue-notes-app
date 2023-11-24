<script>
import Note from "./note.vue";
export default {
  components: {
    Note,
  },
  props: {
    notes: {
      type: Array,
      required: true,
    },
  },
};
</script>

<template>
  <section class="cards-container">
    <Note v-for="{ text, date } in notes" :text="text" :date="date" />
  </section>
</template>
<style scoped>
.cards-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1rem;
}
</style>
