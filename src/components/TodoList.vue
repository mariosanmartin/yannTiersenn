<template>
  <div>
    <h2>Componente 3</h2>
    <form id="app">
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
      newTask: ""
    };
  }
};
</script>

<style></style>
