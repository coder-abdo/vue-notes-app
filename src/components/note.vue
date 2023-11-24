<script>
export default {
  name: "Note",
  props: {
    text: String,
    date: String,
  },
  methods: {
    getBackgroundColor() {
      return `#${Math.floor(Math.random() * 16777215).toString(16)}`;
    },
  },
};
</script>
<template>
  <div class="card" :style="{ backgroundColor: getBackgroundColor() }">
    <h2>{{ text }}</h2>
    <p>{{ date }}</p>
  </div>
</template>
<style scoped>
.card {
  background-color: #fff;
  border-radius: 0.5rem;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  padding: 1rem;
  margin-bottom: 1rem;
}
</style>
