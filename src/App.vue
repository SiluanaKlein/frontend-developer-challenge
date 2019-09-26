<template>
  <v-app>
    <v-content>
      <v-container
        class="pt-0 pl-0 pr-0 pb-0"
        fluid
      >
        <cabecalho />
        <produtos />
        <formulario />
        <rodape />
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import cabecalho from './components/Cabecalho.vue'
import produtos from './components/Produtos.vue'
import formulario from './components/Formulario.vue'
import rodape from './components/Rodape.vue'

export default {
  name: 'App',
  components: {
    cabecalho,
    produtos,
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
