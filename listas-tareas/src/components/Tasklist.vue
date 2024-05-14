<template> 

<v-form>
  <h1>Task List</h1>
  
  <v-text-field type ="text" v-model="newTask" @keyup.enter="addTask"> </v-text-field>
  <button @click="addTask">Add Task</button>

  <ul>
    <li v-for="(task, index) in tasks" :key="index">
      {{ task }}
      <button @click="removeTask(index)">Remove</button>
    </li>
  </ul>
</v-form>

<script>
new Vue({
  el: '#app',
  data: {
    newTask: '',
    tasks: []
  },
  methods: {
    addTask() {
      if (this.newTask.trim() !== '') {
        this.tasks.push(this.newTask);
        this.newTask = '';
      }
    },
    removeTask(index) {
      this.tasks.splice(index, 1);
    }
  }
})
</script>

</template>