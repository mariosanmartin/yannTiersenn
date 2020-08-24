<template>
  <div>
    <!-- <h2>Componente 3</h2> -->
    <form id="app" @submit.prevent="createTask">
      <label class="label" for="task">Nueva Tarea: </label>
      <input type="text" v-model="newTask" id="task" />
      {{ newTask }}
      <input type="submit" value="Crear Tarea" />
      <ul>
        <li
          v-for="(task, i) in tasks"
          :key="`task` + i"
          :class="{ completed: task.completed }"
        >
          {{ task.text }}
        </li>
      </ul>
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
        completed: true
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

<style>
.completed {
  text-decoration: line-through;
  color: gray;
}
</style>
