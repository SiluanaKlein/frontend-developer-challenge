<template>
  <section class="claro pb-8">
    <h2>Sua seleção especial</h2>
    <v-row>
      <v-col
        offset-lg="2"
        offset-md="2"
        offset-sm="1"
        lg="8"
        md="8"
        sm="10"
        cols="12"
      >
        <v-row>
          <produto-item
            v-for="item in produtos"
            :produto="item"
            :key="item.id"
          />

        </v-row>
      </v-col>
    </v-row>
    <v-row>
      <v-col
        offset-lg="5"
        offset-md="5"
        offset-sm="3"
        lg="2"
        md="2"
        sm="6"
        cols="12"
      >
        <v-btn
          type="submit"
          x-large
          block
          outlined
          @click="buscarMais"
          class="custom-btn mb-12"
        >Ainda mais produtos aqui!</v-btn>
      </v-col>
    </v-row>

    <v-overlay :value="overlay">
      <v-progress-circular
        indeterminate
        size="64"
      ></v-progress-circular>
    </v-overlay>

    <v-snackbar
      v-model="snackbar"
      timeout="3000"
    >
      Opss, isso não deveria ter acontecido. Tente novamente mais tarde :(
      <v-btn
        color="error"
        text
        @click="snackbar = false"
      >
        Close
      </v-btn>
    </v-snackbar>
  </section>
</template>

<script>
// importa o axios para fazer a requisição REST
import axios from 'axios'
// componente que contém o template para cada produto
import produtoItem from '@/components/ProdutoItem'
export default {
  name: 'Produtos',
  data: () => ({
    // exibe a mensagem de erro
    snackbar: false,
    // lista de produtos
    produtos: [],

    // exibe o feedback de carregamento
    overlay: false,

    // contador para buscar proximas paginas
    page: 1
  }),
  components: {
    produtoItem
  },
  created () {
    this.buscarMais()
  },
  methods: {
    buscarMais () {
      // habilita a indicação de carregamento
      this.overlay = true
      axios.get(`https://frontend-intern-challenge-api.iurykrieger.now.sh/products?page=${this.page}`)
        .then((response) => {
          // em caso de sucesso soma o contador para que ele busque a próxima página quando solicitado
          this.page++
          // adiciona os novos resultados à nova lista de produtos existente
          this.produtos = this.produtos.concat(response.data.products)
          // finaliza o indicativo de carregamento
          this.overlay = false
        })
        .catch((error) => {
          // em caso de erro finaliza o indicativo de carregamento e exibe uma mensagem de erro
          this.overlay = false
          this.snackbar = true
          console.log(error)
        })
    }
  }
}

</script>

<style scoped>
h2 {
  text-align: center;
}
</style>
