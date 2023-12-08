<script setup>
import { ref } from "vue";

const noteTitle = ref("");
const noteBody = ref("");
// note form complete
const createNote = () => {
  fetch("http://localhost:3000/notes/", {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({ title: noteTitle.value, body: noteBody.value }),
  })
    .then((res) => res.json())
    .then((data) => console.log(data));
};
// .trim and add a check for data
// delete button, its going to have an data-set id, delete function and delete fetch req
</script>

<template>
  <form id="writeNotes" @submit.prevent="createNote">
    <h2>Body Your Thoughts</h2>
    <!--  proves that it binds
    <h1>{{ noteTitle }}</h1> -->

    <label name="title" id="title">Title of Notes</label>
    <input type="text" v-model="noteTitle" />

    <label name="body" id="body">Body of Notes</label>
    <textarea type="text" v-model="noteBody" />

    <button for="btn" action="submit">Post Your Thoughts</button>
  </form>
</template>
