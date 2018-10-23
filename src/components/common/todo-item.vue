<template>
  <li>
    Id: {{ id }} Text:  {{ text }}
    <button v-on:click="$emit('remove')">Remove</button>
  </li>
</template>

<script>
  export default {
    name: "todoItem",
    props: {
      text: String,
      id: Number
    }
  }
</script>
