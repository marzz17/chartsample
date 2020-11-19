<template>
<div>
  <div id="chartContainer" />
 </div>
</template>

<script>
var CanvasJS = require('../plugins/canvasjs.min.js');
CanvasJS = CanvasJS.Chart ? CanvasJS : window.CanvasJS;
export default {
name: 'samplechart',
data() {
  return {
    chartOptions: {
      theme: "light1",
      zoomEnabled: true,
    	title: {
      	text: "Select area to zoom"
      },
      axisX:{
			valueFormatString: "####",
			interval: 1
		},
		axisY:[{
			title: "Linear Scale",
			lineColor: "#369EAD",
			titleFontColor: "#369EAD",
			labelFontColor: "#369EAD"
		},
		{
			title: "Logarithmic Scale",
			logarithmic: true,
			lineColor: "#C24642",
			titleFontColor: "#C24642",
			labelFontColor: "#C24642"
		}],
		axisY2:[{
			title: "Linear Scale",
			lineColor: "#7F6084",
			titleFontColor: "#7F6084",
			labelFontColor: "#7F6084"
		},
		{
			title: "Logarithmic Scale",
			logarithmic: true,
			interval: 1,
			lineColor: "#86B402",
			titleFontColor: "#86B402",
			labelFontColor: "#86B402"
		}],
      data: [
       {
          type: "column",
          showInLegend: true,
          //axisYIndex: 0, //Defaults to Zero
          name: "Axis Y-1",
          xValueFormatString: "####",
          dataPoints: [
            { x: 2006, y: 6 },
            { x: 2007, y: 2 },
            { x: 2008, y: 5 },
            { x: 2009, y: 7 },
            { x: 2010, y: 1 },
            { x: 2011, y: 8 },
            { x: 2012, y: 5 },
            { x: 2013, y: 2 },
            { x: 2014, y: 2 }
          ]
        },
        {
          type: "spline",
          showInLegend: true,
          axisYIndex: 1, //Defaults to Zero
          name: "Axis Y-2",
          xValueFormatString: "####",
          dataPoints: [
            { x: 2006, y: 15 },
            { x: 2007, y: 300 },
            { x: 2008, y: 20 },
            { x: 2009, y: 100 },
            { x: 2010, y: 30 },
            { x: 2011, y: 10 },
            { x: 2012, y: 6000 },
            { x: 2013, y: 20 },
            { x: 2014, y: 245 }
          ]
        },
        {
          type: "column",
          showInLegend: true,                  
          axisYType: "secondary",
          //axisYIndex: 0, //Defaults to Zero
          name: "Axis Y2-1",
          xValueFormatString: "####",
          dataPoints: [
            { x: 2006, y: 12 },
            { x: 2007, y: 2000 },
            { x: 2008, y: 28 },
            { x: 2009, y: 342 },
            { x: 2010, y: 24 },
            { x: 2011, y: 455 },
            { x: 2012, y: 15 },
            { x: 2013, y: 34 },
            { x: 2014, y: 242 }
          ]
        },
        {
          type: "spline",
          showInLegend: true,                  	
          axisYType: "secondary",
          axisYIndex: 1, //When axisYType is secondary, axisYIndex indexes to secondary Y axis & not to primary Y axis
          name: "Axis Y2-2",
          xValueFormatString: "####",
          dataPoints: [
            { x: 2006, y: 86 },
            { x: 2007, y: 15 },
            { x: 2008, y: 27 },
            { x: 2009, y: 78 },
            { x: 2010, y: 46 },
            { x: 2011, y: 70 },
            { x: 2012, y: 50 },
            { x: 2013, y: 60 },
            { x: 2014, y: 50 }
          ]
        }					
      ]
    },
    chart : null,

}
},
mounted: function () {	
	this.chart = new CanvasJS.Chart("chartContainer", this.chartOptions);
    this.chart.render();
  }
}
</script>

<style>

</style>