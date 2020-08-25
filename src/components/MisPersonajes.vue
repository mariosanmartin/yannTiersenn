<template>
  <div>
    <h1>Cantidad Pjs {{ Personajes.length }}</h1>
    <form @submit.prevent="crearPersonaje">
      <label class="label">Nuevo Personaje</label>
      <input class="input" type="text" v-model="nuevoPersonaje" />
      <!-- {{nuevoPersonaje}} -->
      <input class="button" type="submit" value="crear Personaje" />
    </form>
    <ul>
      <li
        class="personajillos"
        v-for="(pj, i) in Personajes"
        :key="`pj` + i"
        :class="{ estado: pj.estado }"
      >
        {{ pj.nombre }} -- {{ pj.raza }}
        <button class="button" @click="personajeEliminado(pj.nombre)">
          {{ mensaje }}
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nuevoPersonaje: "",
      Personajes: [],
      mensaje: "eliminar"
    };
  },
  methods: {
    crearPersonaje() {
      let personaje = {
        nombre: this.nuevoPersonaje,
        raza: "nordo",
        estado: false
      };
      this.Personajes.push(personaje);
      this.nuevoPersonaje = "";
      console.log(this.Personajes);
    },
    personajeEliminado(nombrepj) {
      for (let i = 0; i < this.Personajes.length; i++) {
        let paku = this.Personajes[i];
        if (nombrepj === paku.nombre) {
          paku.estado = !paku.estado;
        }
        if (this.mensaje === "Eliminar") {
          this.mensaje = "Cambiar";
        } else {
          this.mensaje = "Eliminar";
        }
      }
    }
  }
};
</script>

<style scoped>
.personajillos {
  cursor: pointer;
  margin: 10px;
}

.label {
  padding: 10px;
  color: brown;
}
.input {
  margin-right: 20px;
}
.button {
  color: #ecf0f1;
  background-color: #2ecc71;
  border-radius: 5px;
}
.estado {
  text-decoration: line-through;
  color: red;
}
</style>
