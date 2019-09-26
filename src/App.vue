<template>
  <v-app>
    <v-content>
      <cabecalho />
      <formulario />
      <rodape />
    </v-content>
  </v-app>
</template>

<script>
import cabecalho from './components/Cabecalho.vue'
import formulario from './components/Formulario.vue'
import rodape from './components/Rodape.vue'

export default {
  name: 'App',
  components: {
    cabecalho,
    formulario,
    rodape
  },
  data: () => ({
    //
  })
}
</script>

<style lang="scss">
@import "./assets/css/app.scss";
</style>
