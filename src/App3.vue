<script setup>
import { ref, onMounted } from 'vue';

const name = ref('Franz');
const status = ref('active');
const tasks = ref(['Asado', 'Fernet', 'Birra']);
const link = ref('https://www.google.com/');
const newTask = ref('');
const toggleStatus = () => {

  if (status.value === 'active') {
    status.value = 'pending'
  }

  else if
    (status.value === 'pending') {
    status.value = 'inactive'
  }

  else {
    status.value = 'active'
  }
}

const addTask = () => {
  if (newTask.value.trim() !== '') {
    tasks.value.push(newTask.value)
  }
  newTask.value = '';
};

const deleteTask = (index) => {
  tasks.value.splice(index, 1)

};
onMounted(async () => {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/todos?_limit=10');
    const data = await response.json();
    tasks.value = data.map((task) => task.title);
  } catch (error) {
    console.log(error);
  }
})
</script>
<template>

  <h1 v-if="status === 'active'">Active {{ name }}</h1>
  <h1 v-else-if="status === 'pending'"> Pending</h1>
  <h1 v-else="status"> Inactive </h1>


  <form @submit.prevent="addTask">
    <label for="newTask">Add Task</label>
    <input type="text" name="newTask" id="newTask" v-model="newTask">


    <button type="submit">Send Form</button>
  </form>




  <h3>Tasks</h3>
  <ul>
    <li v-for="(task, index) in tasks" :key="task">
      <span>
        {{ task }}
      </span>
      <button @click="deleteTask(index)">Delete</button>
    </li>
  </ul>

  <!-- Events -->
  <button v-on:click="toggleStatus">Change Status</button>
  <!-- Or -->
  <button @click="toggleStatus">Change Status</button>


</template>
