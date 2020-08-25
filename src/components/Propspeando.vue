<template>
  <div>
    <h2>Desde Propspero</h2>
    <hr />
    <p>Tratando de entender los Props</p>
    <span>Filas : {{ filas }} , columnas {{ columnas }}</span>
    <br />
    {{ titulo }}
    <!-- this.$router.push({ name: 'users', params: {title: 'test title' }}) -->
  </div>
</template>

<script>
export default {
  props: {
    columnas: {
      type: Number,
      default: 4
    },
    filas: {
      type: Number,
      default: 3
    },
    titulo: {
      type: String,
      default:
        "Madara Uchija es el mejor a pesar que no e visto Naruto Shippudent"
    }
  },
  computed: {
    totalMeses() {
      return this.columnas * this.filas;
    }
  }
};
</script>
