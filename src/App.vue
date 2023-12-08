<script setup>

import NotesList from "./assets/components/NotesList.vue"


</script>

<template>
  <div>
    <h1>CarolineLovesVueNotes</h1>
    <!-- your code here -->

    <form id="writeNotes">
      <h2>Body Your Thoughts</h2>

      <label name="title" id="title">Title of Notes</label>
      <input :value="text" @input="(event) => (text = event.target.value)" />

      <label name="body" id="body">Body of Notes</label>
      <textarea v-model="text" />

      <button for="btn" action="submit">Post Your Thoughts</button>
    </form>
    
    <NotesList />

  </div>
</template>

<style scoped></style>
