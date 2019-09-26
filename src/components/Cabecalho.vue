<template>
  <v-container
    class="pt-0 pl-0 pr-0"
    fluid
  >
    <header class="escuro pb-12 pt-12">
      <div class="text-center">
        <h1>
          <span class="h1-discreto">uma seleção de produtos</span>
          <br>
          <span class="h1-destacado">especial para você</span>
        </h1>
        <p class="mt-6 mb-6">Todos os produtos desta lista foram selecionados a partir da sua navegação. Aproveite!</p>
      </div>

      <v-row class="pt-6 mb-6">
        <v-col
          lg="2"
          md="3"
          sm="6"
          offset-lg="2"
          cols="12"
          class="text-center"
        >
          <v-btn
            class="custom-btn"
            width="85%"
            large
          >
            Conheça a Linx
          </v-btn>
        </v-col>

        <v-col
          lg="2"
          md="3"
          sm="6"
          cols="12"
          class="text-center"
        >
          <v-btn
            class="custom-btn"
            width="85%"
            large
          >
            Ajude o algorítimo
          </v-btn>
        </v-col>

        <v-col
          lg="2"
          md="3"
          sm="6"
          cols="12"
          class="text-center"
        >
          <v-btn
            class="custom-btn"
            width="85%"
            large
          >
            Seus produtos
          </v-btn>
        </v-col>

        <v-col
          lg="2"
          md="3"
          sm="6"
          cols="12"
          class="text-center"
        >
          <v-btn
            class="custom-btn"
            width="85%"
            large
          >
            Compartilhe
          </v-btn>
        </v-col>
      </v-row>
    </header>
  </v-container>
</template>

<script>
export default {
  name: 'Cabecalho'

}
</script>

<style scoped>
.h1-discreto {
  font-weight: 350;
  font-size: 22px;
}

.h1-destacado {
  font-size: 45px;
}
h1 {
  line-height: 1.2;
}
p {
  font-size: 18px;
}
</style>
