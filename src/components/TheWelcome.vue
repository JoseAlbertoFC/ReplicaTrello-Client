<script setup>
import { ref } from 'vue'

const project = ref({
  name: '',
  description: '',
  startDate: '',
  endDate: ''
})

const submitProject = () => {
  console.log('Project submitted:', project.value)
}
</script>

<template>
  <div class="form-container">
    <form @submit.prevent="submitProject">
      <h2 class="title">New Project</h2>
      <div class="input-group">
        <label for="name">Project Name:</label>
        <input id="name" v-model="project.name" type="text" required>
      </div>
      <div class="input-group">
        <label for="description">Project Description:</label>
        <textarea id="description" v-model="project.description" required></textarea>
      </div>
      <div class="input-group">
        <label for="start-date">Start Date:</label>
        <input id="start-date" v-model="project.startDate" type="date" required>
      </div>
      <div class="input-group">
        <label for="end-date">End Date:</label>
        <input id="end-date" v-model="project.endDate" type="date" required>
      </div>
      <button type="submit">Crear</button>
    </form>
  </div>
</template>

<style>
.title {
  color:rgb(57, 214, 135);
  font-weight: 20px;
}

.form-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 70vh;
  background-color: #434947;
  padding: 20px;
  margin-top: 25px;
  border-radius: 20px;
}

form {
  background: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  max-width: 500px;
  width: 100%;
}

.input-group {
  margin-bottom: 15px;
  text-align: left;
}

input[type="text"],
input[type="date"],
textarea,
button {
  width: 100%;
  padding: 10px;
  margin-top: 5px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  background-color: #22da8d;
  color: white;
  border: none;
  cursor: pointer;
  margin-top: 10px;
}

button:hover {
  background-color: #148f60;
}

input[type="text"]:focus,
input[type="date"]:focus,
textarea:focus {
  outline: none;
  border-color: #007bff;
  box-shadow: 0 0 0 2px rgba(0,123,255,.25);
}
</style>




