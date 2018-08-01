<template>
  <div>
    <h1>Imóveis para alugar</h1>

    <v-text-field label="Fiter by City" prepend-icon="search" v-model="termoPesquisa" @keyup="filtrar()"></v-text-field>

    <v-layout>
      <imovel :imovel="meuImovel" v-for="meuImovel in imoveis" :key="meuImovel.id"></imovel>
    </v-layout>
  </div>
</template>

<script>
import Imovel from '@/components/Imovel'

export default {

  components: { Imovel },

  data () {
    return {
      imoveis: [],
      termoPesquisa: null,
    }
  },
  mounted () {
    this.carregar()
  },
  methods: {
    carregar (params) {
      this.$axios.get('/imoveis', { params }).then(response => {
        this.imoveis = response.data
      })
    },
    filtrar () {
      this.carregar({ city: this.termoPesquisa })
    }
  }
}
</script>

<style scoped>
h1 {
  color: black;
}

input {
  padding: 10px;
  width: 600px;
  border: 1px #c0c0c0 solid;
  display: block;
  margin: 20px;
}
</style>