<template>
  <div>
    <MisPersonajes />
    <Prospero :columnas="columnas" :filas="filas" />
    <Prospero :text="resultado" />
    <Prospero :columnas="17" :filas="71" />
    <Prospero :columnas="12" :filas="77" />
  </div>
</template>
<script>
import MisPersonajes from "@/components/MisPersonajes.vue";
import Prospero from "@/components/Propspeando.vue";
export default {
  components: {
    MisPersonajes,
    Prospero
  },
  data() {
    return {
      columnas: 7,
      filas: 77
    };
  },
  computed: {
    resultado() {
      return "columnas: " + this.columnas + "filas: " + this.filas;
    }
  }
};
</script>
