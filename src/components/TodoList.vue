<template>
  <div class="task-list">
    <h2>{{ tasks.length }} Tasks</h2>
    <form class="form" @submit.prevent="createTask">
      <label class="label" for="task">Nueva Tarea: </label>
      <input class="input" type="text" v-model="newTask" id="task" />
      <!-- {{ newTask }} -->
      <input class="button" type="submit" value="Crear Tarea" />
    </form>
    <ul class="list">
      <li
        class="task"
        v-for="(task, i) in tasks"
        :key="`task` + i"
        :class="{ completed: task.completed }"
        @click="completedTask(task.text)"
      >
        {{ task.text }}
      </li>
    </ul>
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
    },
    completedTask(taskText) {
      for (let i = 0; i < this.tasks.length; ++i) {
        let task = this.tasks[i];
        if (taskText === task.text) {
          task.completed = !task.completed;
        }
      }
    }
  }
};
</script>

<style scoped>
.task-list {
  width: 800px;
  max-width: 100%;
  margin: 0px auto;
}
.form {
  background: white;
  border-radius: 12px;
  padding: 30px;
  box-shadow: 2px 10px 22px 10px rgba(0, 0, 0, 0.25);
  margin-top: 10px;
}
.label {
  display: block;
  margin-bottom: 10px;
}
.input {
  height: 35px;
}
.button {
  margin-left: 20px;
  height: 35px;
  border: none;
  border-radius: 5px;
  box-shadow: 5px 1px 4px rgba(0, 0, 0, 2);
  background-color: #2ecc71;
  color: #ecf0f1;
  cursor: pointer;
}
.list {
  margin-top: 30px;
}
.task {
  cursor: pointer;
  margin: 10px 0;
}
.completed {
  text-decoration: line-through;
  color: lightgrey;
}
</style>
