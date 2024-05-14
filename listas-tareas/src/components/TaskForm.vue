<template>
    <v-form>
    <v-text-field v-model="taskName" label="Nombre de la tarea" required></v-text-field>
    <v-textarea v-model="taskDescription" label="Descripción"></v-textarea>
    <v-btn @click="addTask">Agregar Tarea</v-btn>
    </v-form>
    </template>
     
    <script>
    export default {
      data() {
        return {
          taskName: '',
          taskDescription: ''
        };
      },
      methods: {
        addTask() {
          this.$emit('add-task', {
            name: this.taskName,
            description: this.taskDescription,
            completed: false,
            dateCreated: new Date().toISOString()
          });
          this.taskName = '';
          this.taskDescription = '';
        }
      }
    }
    </script>