<template>
  <v-col
    lg="3"
    md="3"
    sm="4"
    cols="12"
    class="claro pad"
  >
    <div class="text-center custom-border">
      <img
        :src="`http:${produto.image}`"
        alt="${p.name}"
      >

    </div>
    <h3>{{produto.name}}</h3>
    <p>{{produto.description}}</p>
    <p>{{ `De: R$${parseFloat(produto.oldPrice).toLocaleString('pt-BR',{useGrouping: true, minimumFractionDigits: 2})}` }}</p>
    <p class="preco">{{ `Por: R$${parseFloat(produto.oldPrice).toLocaleString('pt-BR',{useGrouping: true, minimumFractionDigits: 2})}` }}</p>
    <p>{{`ou ${produto.installments.count}x de R$${parseFloat(produto.installments.value).toLocaleString('pt-BR',{useGrouping: true, minimumFractionDigits: 2})}` }}</p>
    <v-btn
      block
      outlined
      class="custom-btn"
    >comprar</v-btn>
  </v-col>
</template>

<script>
export default {
  name: 'ProdutoItem',
  props: ['produto']
}
</script>

<style scoped>
h3 {
  margin-top: 14px;
  font-weight: 450;
  margin-bottom: 10px;
}
p {
  margin-bottom: 8px !important;
}

.preco {
  font-weight: bolder;
  font-size: 20px;
}

.pad {
  padding: 25px;
}
.custom-border {
  border: 1px solid #707070;
  padding-top: 10px;
  padding-bottom: 10px;
}
</style>
