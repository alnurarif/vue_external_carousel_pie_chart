<script setup>

import { onMounted, onBeforeUnmount } from 'vue'

let pieChart = null

const dataset = [330,520,150,400]

// Sample data for the Pie Chart
const data = {
  labels: [
    'Red',
    'Blue',
    'Yellow',
    'Green'
  ],
  datasets: [{
    label: 'My First Dataset',
    data: dataset,
    backgroundColor: [
      'rgb(255, 99, 132)',
      'rgb(54, 162, 235)',
      'rgb(255, 205, 86)',
      'rgb(34, 139, 34)'
    ],
    hoverOffset: 4
  }]
}

const config = {
    type : 'pie',
    data : data
}
onMounted(() => {
    const pieChartCanvas = document.getElementById('pieChart')
    pieChart = new Chart(pieChartCanvas,config)

})
onBeforeUnmount(() => {
  pieChart.destroy()
  console.log('onBeforeUnmounted : pie chart')
  
})

</script>

<template>
    <div class="carousel_wrapper" >
        <canvas id="pieChart"></canvas>
    </div>
</template>

<style scoped>
#pieChart{
  margin:0 auto;
}
</style>