<script>
export default {
  data() {
    return {
      name: 'Franz',
      status: 'active',
      tasks: ['Asado', 'Fernet', 'Birra'],
      link: 'https://www.google.com/',
    };
  },
  methods: {
    toggleStatus() {
      if (this.status === 'active') {
        this.status = 'pending'
      }
      else if
        (this.status === 'pending') {
        this.status = 'inactive'
      }
      else {
        this.status = 'active'
      }
    },
  },
};
</script>

<template>
  <h1 v-if="status === 'active'">Active {{ name }}</h1>
  <h1 v-else-if="status === 'pending'"> Pending</h1>
  <h1 v-else="status"> Inactive </h1>

  <h3>Tasks</h3>
  <ul>
    <li v-for="task in tasks" :key="task"> {{ task }}</li>
  </ul>

  <!-- V-Bind -->
  <a :href="link"> Click for Google</a>

  <!-- Events -->
  <button v-on:click="toggleStatus">Change Status</button>
  <!-- Or -->
  <button @click="toggleStatus">Change Status</button>


</template>
