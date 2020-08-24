<template>
  <div>
    <!-- <h2>Componente 3</h2> -->
    <form id="app" @submit.prevent="createTask">
      <label class="label" for="task">Nueva Tarea: </label>
      <input type="text" v-model="newTask" id="task" />
      {{ newTask }}
      <input type="submit" value="Crear Tarea" />
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTask: "",
      tasks: []
    };
  },
  methods: {
    createTask() {
      let task = {
        text: this.newTask,
        completed: false
      };
      // Mete la tarea en el array tareas
      this.tasks.push(task);
      // y luego limpiamos el text
      this.newTask = "";
      console.log(this.tasks);
    }
  }
};
</script>

<style></style>
