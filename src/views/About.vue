<template>
  <div class="about">
    <h1>Conceptos desde Componentes</h1>
    <SobreMi />
    <eje-computed />
  </div>
</template>
<script>
import SobreMi from "@/components/SobreMi.vue";
import EjeComputed from "@/components/EjeComputed.vue";
export default {
  components: {
    SobreMi,
    EjeComputed
  }
};
</script>
