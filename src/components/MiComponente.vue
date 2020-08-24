<template>
  <div>
    <h2>Desde Componente 1 | conceptos basicos</h2>
    <p>Probando hasta cierto puntos la reactividad de Vue</p>
    <!-- <p v-if="condicion">Este mensaje se mostrara</p> -->
    <ul v-if="condicion">
      <li>Madara el mas picante de todos</li>
      <li>El papi del caos , sin lugar a dudas.</li>
    </ul>

    <p v-else-if="list.length !== 5 && list[0] === 0">
      Este mensaje esta maldito
    </p>
    <p v-else>
      Este si mensaje si que esta maldito loco!!!
    </p>
    <img :src="pic" :class="poto" />

    <div :style="estiloso">
      <ul>
        <li v-for="(item, i) in weichafes" :key="i">
          id:
          {{ item.id }}
          -
          {{ item.name }} | Poderes:
          <span v-for="(poder, k) in item.poderes" :key="`podercito` + k">
            {{ poder }}
          </span>
        </li>
      </ul>
    </div>

    {{ calcular() }} | {{ calcular() }} |
    {{ calcular() }}

    <!-- {{ miVariable }} -->
  </div>
</template>

<script>
//Variable global
let total = 0;
export default {
  name: "MiComponente",
  data() {
    return {
      miVariable: "Hola Madara Uchija",
      condicion: false,
      list: [0, 2, 3, 4, 5],
      weichafes: [
        { name: "Lautaro", id: 1, poderes: ["tierra", "aire"] },
        { name: "Kalfukura", id: 2, poderes: ["susano", "perfecto"] },
        { name: "Caupolican", id: 3, poderes: ["perro", "kk"] }
      ],
      pic: "https://i.imgur.com/BBcy6Wc.jpg",
      poto: {
        active: true,
        "text-danger": false
      },
      estiloso: {
        background: "red",
        width: "300px",
        height: "30px",
        fontSize: "20px"
      },
      valorius: 20
    };
  },
  methods: {
    calcular() {
      // let auxiliar = this.valorius * 2;
      total++;
      return total;
      // return this.valorius * 2;
      // console.log(auxiliar);
    }
  }
};
</script>

<style lang="scss" scoped></style>
