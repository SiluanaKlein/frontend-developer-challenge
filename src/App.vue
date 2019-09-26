<template>
  <v-app>
    <v-content>
      <cabecalho />
    </v-content>
  </v-app>
</template>

<script>
import cabecalho from './components/Cabecalho.vue'

export default {
  name: 'App',
  components: {
    cabecalho
  },
  data: () => ({
    //
  })
}
</script>

<style lang="scss">
@import "./assets/css/app.scss";
</style>
