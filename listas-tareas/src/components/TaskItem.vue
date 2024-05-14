<template> 

<v-form>
    <v-text-field v-model="newTask"  required></v-text-field>
    <v-textarea v-model="addTask" ></v-textarea>
    <v-btn @click="addTask">Agregar Tarea</v-btn>
</v-form> 

    <ul>
      <task-item v-for="(task, index) in tasks" :key="index" :task="task" :index="index" @remove="removeTask"></task-item>
    </ul>
 
  
  <script>
   export default {
      data() {
        return {
          newTask: '',
          addTask: ''
        };
      },
  
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
}
  </script>
  
</template>