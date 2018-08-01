<template>
  <v-flex xs4 class="ma-2">
    <v-card>
      <v-card-media :src="imovel.image" height="200px">
      </v-card-media>
      <v-card-title primary-title>
        <div>
          <h3 class="headline mb-0">{{ imovel.title }}</h3>
          <div>
            <strong>Owner</strong>: {{ imovel.owner}} </div>
          <div>
            <strong>Location</strong>: {{ imovel.location}} </div>
          <div>
            <strong>Bedromns</strong>: {{ imovel.bedrooms}} </div>
        </div>
      </v-card-title>
      <v-card-actions>
        <v-btn flat color="orange">Explore</v-btn>
      </v-card-actions>
    </v-card>
  </v-flex>
</template>

<script>
export default {
  // declara quais as propriedades recebidas pelo componente
  props: ['imovel']
}
</script>

<style scoped>
.bloco {
  background: #efefef;
  margin: 20px;
  padding: 20px;
  float: left;
}

.bloco img {
  max-height: 100px;
}
</style>