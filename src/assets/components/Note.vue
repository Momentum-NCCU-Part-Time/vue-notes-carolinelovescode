<script setup>
const notes = ref([]);
fetch("http://localhost:3000/notes/", {
  method: "GET",
  headers: { "Content-Type": "application/json" },
})
  .then((res) => res.json())
  .then((data) => (notes.value = data));
</script>

<template>
  <li v-for="note in notes">
    {{ note.title }}
    {{ note.body }}
  </li>
</template>
