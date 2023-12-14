<script setup>
import { ref } from "vue";
import NoteForm from "./NoteForm.vue";

const notes = ref([]);

// const apiNote = "http://localhost:3000/notes/";

// get request is adding title and body (you can make into a new component with the NoteForm)
fetch("http://localhost:3000/notes/", {
  method: "GET",
  headers: { "Content-Type": "application/json" },
})
  .then((res) => res.json())
  .then((data) => (notes.value = data));
</script>

<template>
  <NoteForm />
  <div class="listOfNotes">
    <h2>All of Your Thoughts</h2>
    <ul>
      <!--instead of this you can render a note comp, a v-for, then the note component would do this with the delete and edit-->
      <li v-for="note in notes">
        {{ note.title }}
        {{ note.body }}
        <!-- {{ note.updatedAt }} -->
      </li>
      <note-single
        v-for="note in notes"
        :key="note.id"
        :note="note"
        @remove="deleteNote"
      />
    </ul>
  </div>
</template>
//
