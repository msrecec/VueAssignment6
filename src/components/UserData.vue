// Task 1: // Add two components to the app: // An ActiveUser component and an
UserData component // ActiveUser should output a username (h2) and age (h3) //
UserData should output two input fields => for name and age // Optional: Add
styling of your choice

<template>
  <form @submit.prevent="submitData">
    <div>
      <label>Name</label>
      <input type="text" v-model="enteredName" />
    </div>
    <div>
      <label>Age</label>
      <input type="number" v-model="enteredAge" min="0" max="150" />
    </div>
    <div>
      <button>Add User</button>
    </div>
  </form>
</template>

<script>
export default {
  emits: ['add-user'],
  data() {
    return {
      enteredName: '',
      enteredAge: 0,
    };
  },
  methods: {
    submitData() {
      this.$emit('add-user', this.enteredName, this.enteredAge);
    },
  },
};
</script>
