<script setup>
import { ref } from "vue";
const notes = ref([]);

fetch("http://localhost:3000/notes/", {
  method: "GET",
  headers: { "Content-Type": "application/json" },
})
  .then((res) => res.json())
  .then((data) => (notes.value = data));
</script>
<template>
  <div class="listOfNotes">
    <h2>All of Your Thoughts</h2>
    <ul>
      <li v-for="note in notes">
        {{ note.title }}
        {{ note.body }}
      </li>
    </ul>
  </div>
</template>
