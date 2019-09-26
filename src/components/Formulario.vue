<template>
  <section class="claro pl-2 pr-2 pb-12">
    <div class="text-center mb-7">
      <h2>Compartilhe a novidade</h2>
      <p>Quer que seus amigos também ganhem a lista personalizada deles? Preencha agora!</p>
    </div>
    <v-form>
      <v-row>
        <v-col
          lg="4"
          md="4"
          sm="6"
          offset-md="2"
          offset-lg="2"
          cols="12"
        >
          <label for="nome">Nome do seu amigo</label>
          <v-text-field
            class="custom-input"
            outlined
            required
            type="text"
            name="nome"
          ></v-text-field>
        </v-col>

        <v-col
          lg="4"
          md="4"
          sm="6"
          cols="12"
        >
          <label for="email">E-mail</label>
          <v-text-field
            name="email"
            class="custom-input"
            outlined
            required
            type="email"
          ></v-text-field>
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
            class="custom-btn mt-12"
          >Enviar agora</v-btn>
        </v-col>
      </v-row>
    </v-form>
  </section>
</template>

<script>
export default {
  name: 'Formulario'
}
</script>

<style scoped>
</style>
