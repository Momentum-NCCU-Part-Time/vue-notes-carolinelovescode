<script setup>
const notes = [
  {
    id: 1,
    title: "Sample note",
    body: "This is the body of my note",
    updatedAt: "2018-01-01T00:00:00.000Z",
  },
  {
    id: 2,
    title: "This is the beginning",
    body: "Trial One of getting your notes app to work like it should!",
    updatedAt: "2018-01-01T00:00:00.000Z",
  },
];
</script>

<template>
  <div>
    <h1>CarolineLovesVueNotes</h1>
    <!-- your code here -->

    <form id="writeNotes">
      <h2>Body Your Thoughts</h2>

      <label for="title" id="title">Title of Notes</label>
      <input :value="text" @input="(event) => (text = event.target.value)" />

      <label for="body" id="body">Body of Notes</label>
      <textarea v-model="text" />

      <button for="btn">Post Your Thoughts</button>
    </form>
    <div class="listOfNotes">
      <h2>All of Your Thoughts</h2>
      <ul v-for="note in notes">
        {{
          note.title
        }}
        {{
          note.body
        }}
      </ul>
    </div>
  </div>
</template>

<style scoped></style>
