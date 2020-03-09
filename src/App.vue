<template>
  
  <div id="app">
    <canvas id="planet-chart"></canvas>
  </div>
</template>


<script>
// import HelloWorld from './components/HelloWorld.vue'
import chart from "chart.js";
import planetChartData from './chart-data.js';

export default {
  

  methods: {
  createChart(chartId, chartData) {
    const ctx = document.getElementById(chartId);
    const myChart = new chart(ctx, {
      type: chartData.type,
      data: chartData.data,
      options: chartData.options,
    });
    myChart;
  }
},
data() {
  return {
    planetChartData: planetChartData,
  }
},mounted() {
  this.createChart('planet-chart', this.planetChartData);
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
