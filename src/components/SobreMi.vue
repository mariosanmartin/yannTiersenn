<template>
  <div>
    <h2>Desde Componente 2 || Methods</h2>
    <p>Probando a simples rasgos los metodos y su reactividad</p>
    <h3>Metodo calcular</h3>
    <button @click="calcular()">Calcular</button>
    <hr />
    <span @click="calcular()">Calcular desde Span</span>
    <hr />
    <h3>Metodo Incremenetal</h3>
    <button @click="incremento()">Incrementar</button>
    <br />
    <span>Aumentando Valor : {{ valor }}</span>
  </div>
</template>
<script>
export default {
  data() {
    return {
      valor: 20
    };
  },
  methods: {
    calcular() {
      let auxiliar = this.valor;
      console.log(this.double(auxiliar));
    },
    double(valor) {
      return valor * 2;
    },
    incremento() {
      this.valor++;
      // console.log(this.valor);
    }
  }
};
</script>
