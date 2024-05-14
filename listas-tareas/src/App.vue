<template>
  <v-form>
    <h1>Task List</h1>
  
    <v-text-field type="text" v-model="newTask" @keyup.enter="addTask" class="input-field"></v-text-field>
    <button @click="addTask" class="add-button">Añadir Tarea</button>

    <ul>
      <li v-for="(task, index) in tasks" :key="index" class="task-item">
        {{ task }}
        <button @click="removeTask(index)" class="remove-button">Remove</button>
      </li>
    </ul>
  </v-form>
</template>

<script>
import Tasklist from './components/Tasklist.vue'; 

{
  export default{

  data() {
    return {
      newTask: '',
      tasks: []
    };

  },
}
  
};
</script>

<style>
.input-field {
  margin-bottom: 10px;
}

.add-button {
  background-color: #4caf50;
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
}

.task-item {
  margin-bottom: 5px;
}

.remove-button {
  background-color: #f44336;
  color: white;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
}
</style>