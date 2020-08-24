<template>
  <div>
    <h2>Componente 3</h2>
    <hr />
    <p>
      Probando las propiedades Computadas o Computed | Nota: no puedes crear una
      variable en el data cuyo valor sea el doble de otra variable
    </p>
    <hr />
    <p>
      Es importante saber que las computadas nunca pueden recibir un parámetro
      desde fuera de la función. Si necesitas pasar un valor a una computada
      tienes que crear un método.
    </p>
    <hr />
    <p>
      Dentro de cada computada con el this accedemos a los valores del data o a
      los métodos que necesitemos.
    </p>
    <hr />
    <span>Desde el computed que lo trata como una variable {{ doble }} </span>
    <br />
    <span
      >Desde el method que lo trata igual como variable al computed
      {{ calculo() }}</span
    >
  </div>
</template>

<script>
export default {
  data() {
    return {
      valor: 7
    };
  },
  computed: {
    doble() {
      return this.valor * 2;
    }
  },
  methods: {
    calculo() {
      return this.doble + 1;
    }
  }
};
</script>
