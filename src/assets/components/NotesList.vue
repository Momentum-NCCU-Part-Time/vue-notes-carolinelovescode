<script setup>
import { ref } from "vue";
import NoteForm from "./NoteForm.vue";
import Note from "./Note.vue";

// const apiNote = "http://localhost:3000/notes/";

// get request is adding title and body (you can make into a new component with the NoteForm)
</script>
<template>
  <NoteForm />
  <div class="listOfNotes">
    <h2>All of Your Thoughts</h2>
    <ul>
      <!-- instead of this you can render a note comp, a v-for, then the note component would do this with the delete and edit -->
      <Note v-for="note in notes" />
    </ul>
  </div>
</template>
//
