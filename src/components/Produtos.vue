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
            v-for="item in items"
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
  </section>
</template>

<script>
import axios from 'axios'
import produtoItem from '@/components/ProdutoItem'
export default {
  name: 'Produtos',
  data: () => ({
    items: [],
    overlay: false,
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
      this.overlay = true
      axios.get(`${process.env.VUE_APP_URL}/products?page=${this.page}`)
        .then((response) => {
          this.page++
          this.items = this.items.concat(response.data.products)
          this.overlay = false
        })
        .catch((error) => {
          this.overlay = false
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
