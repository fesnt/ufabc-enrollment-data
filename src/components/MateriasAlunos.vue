<template>
  <div>
    <div v-if="loading">
      Desenhando o gráfico :)
    </div>

    <div v-if="error">
      {{ error }}
    </div>

    <div v-if="response">
      <mu-paper class="chart-paper" :zDepth="3">
        <bar-chart :response-data=response.body label="Matérias por Aluno"></bar-chart>
      </mu-paper>
    </div>
  </div>
</template>

<script>
  import './barChart.js'
  import routeDataFetching from '../mixins/routeDataFetching'
  export default {
    name: 'materias-alunos',
    mixins: [routeDataFetching]
  }
</script>

<style>
.chart-paper {
  margin: 20px;
}
</style>
