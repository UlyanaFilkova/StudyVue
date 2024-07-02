<script setup>
import { ref, onMounted } from "vue";

const name = ref("John Doe");
const status = ref(true);
const tasks = ref(["first task", "second task", "third task"]);
const newTask = ref(""); // пустая строка по умолчанию, сразу будет написана в инпуте
const toggleStatus = () => {
  status.value = !status.value;
};
const addTask = () => {
  if (newTask.value.trim() !== "") {
    tasks.value.push(newTask.value);
  }
};
const deleteTask = (index) => {
  tasks.value.splice(index, 1);
};

onMounted(async () => {
  // fetching data and adding it to tasks
});
</script>

<template>
  <h1>{{ status }}</h1>
  <button @click="toggleStatus">change status</button>
  <ul>
       
    <li v-for="(task, index) in tasks" :key="task">
      <span>{{ task }}</span>
      <button @click="deleteTask(index)">x</button>
    </li>
     
  </ul>
  <form @submit.prevent="addTask">
    <input type="text" v-model="newTask" />
  </form>
</template>
