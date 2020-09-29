// Task 2: Output both components side-by-side in your main App template // Task
3: Add user data and ensure it contains a name and age // User data should be
output in ActiveUser // It should be updated via the UserData component

<template>
  <section>
    <user-data @add-user="addUser"></user-data>
    <ul>
      <li>
        <active-user
          v-for="user in users"
          :key="user.id"
          :id="user.id"
          :name="user.name"
          :age="user.age"
        ></active-user>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      users: [
        {
          id: 'mimi',
          name: 'Mislav',
          age: 25,
        },
        {
          id: 'dodo',
          name: 'Domagoj',
          age: 18,
        },
      ],
    };
  },
  methods: {
    addUser(name, age) {
      const newUser = {
        id: new Date().toISOString(),
        name: name,
        age: parseInt(age),
      };
      this.users.push(newUser);
    },
  },
};
</script>
