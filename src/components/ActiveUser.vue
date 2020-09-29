// Task 1: // Add two components to the app: // An ActiveUser component and an
UserData component // ActiveUser should output a username (h2) and age (h3) //
UserData should output two input fields => for name and age // Optional: Add
styling of your choice

<template>
  <h2>{{ name }}</h2>
  <h3>{{ age }}</h3>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    age: {
      type: Number,
      required: true,
    },
  },
};
</script>
