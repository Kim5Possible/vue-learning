<script>
export default {
  data() {
    return {
      name: "John",
      status: "active",
      tasks: ["Task 1", "Task 2", "Task 3"],
      http: "https://google.com",
    };
  },
  methods: {
    toggleStatus() {
      this.status === "active"
        ? (this.status = "pending")
        : this.status === "pending"
        ? (this.status = "inactive")
        : (this.status = "active");
    },
  },
};
</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is not active</p>

  <h3>Tasks:</h3>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>

  <!-- <a v-bind:href="http">Google</a> -->
  <a :href="http">Google</a>
  <br />
  <!-- <button v-on:click="toggleStatus">Change Status</button> -->
  <button @click="toggleStatus">Change Status</button>
</template>

<style scoped></style>
