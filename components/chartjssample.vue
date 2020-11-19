<template>
  <div>
      <canvas id="myChart" width="900" height="300"></canvas>
  </div>
</template>

<script>
import Chart from 'chart.js';
export default {
name: 'chartjssample',
data() {
  return {}
},
mounted: function () {	
	var ctx = document.getElementById('myChart');
        var lineChartData = {
                labels: [2010, 2011, 2012, 2013, 2014, 2015],
                datasets: [{
                    label: '# of Candidates',
                    data: [120, 19, 3, 5, 2, 3],
                    fill: false,
                    backgroundColor: 'rgba(75, 192, 192, 1)',
                    borderColor: 'rgba(75, 192, 192, 1)',
                    borderWidth: 1,
                    yAxisID: "y-axis-1",
                },
                {
                    label: '# of Voters',
                    data: [222, 1, 56, 5, 90, 3000],
                    fill: false,
                    borderColor: 'rgba(255, 99, 132, 1)',
                    borderWidth: 1,
                    yAxisID: "y-axis-2"
                }]
        };

        var myChart = new Chart(ctx, {
            type: 'line',
            data: lineChartData,
            options: {
                responsive: true,
                hoverMode: 'index',
                stacked: false,
                title:{
                    display: true,
                    text:'Votes Data Visualization'
                },
                scales: {
                    yAxes: [{
                        type: "linear", // only linear but allow scale type registration. This allows extensions to exist solely for log scale for instance
                        display: true,
                        position: "left",
                        id: "y-axis-1",
                    }, {
                        type: "linear", // only linear but allow scale type registration. This allows extensions to exist solely for log scale for instance
                        display: true,
                        position: "right",
                        id: "y-axis-2",

                        // grid line settings
                        gridLines: {
                            drawOnChartArea: false, // only want the grid lines for one axis to show up
                        },
                    }],
                }
            }
        });
  }
}

</script>

<style>

</style>