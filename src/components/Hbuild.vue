<template>
  <div>
    <highcharts :options="chartOptions" :callback="myCallback" style="wight:100px"></highcharts>
  </div>
</template>

<script>
export default {
  name: "Hbuild",
  data() {
    return {
      chartOptions: {
          chart: {
		type: 'column'
	},
        title: {
         
        },
        subtitle: {
         
        },
         xAxis: {
		categories: ['2020/4', '2020/6', '2020/8', '2020/10', '2020/12']
  },
        yAxis: {
             max:0.9,
    min:-0.9,
    tickInterval:0.3,
        },
        legend: {
          layout: "vertical",
          align: "right",
          verticalAlign: "middle"
        },
        colors:[
'#bbcbfb',
'#bbcbfb',
'#bbcbfb',
'#bbcbfb',
'#bbcbfb',
'#bbcbfb',
  ],
       
        series: [
          {
		name: '2020/4',
		data: [-0.5, 0.4, 0.3,0.1, -0.6]
	}, {
		name: '2020/6',
		data: [-0.2, -0.3, 0.3, 0.2, -0.1]
	}, {
		name: '2020/8',
		data: [0.3, -0.4, 0.4, -0.2, 0.5]
  },
  {
		name: '2020/10',
		data: [0.3, -0.2, 0.1, 0.1, 0.6]
  },{
		name: '2020/8',
		data: [-0.4, -0.1, 0.4, 0.3,0.5]
  },{
		name: '2020/8',
		data: [0.1,-0.5 , 0.6, -0.2,- 0.2]
  },{
		name: '2020/8',
		data: [-0.3, 0.4, -0.4, -0.2, 0.5]
  },{
		name: '2020/8',
		data: [0.6, -0.5, 0.1, -0.4, 0.2]
  },{
		name: '2020/8',
		data: [-0.1, 0.2,0.5, -0.6,0.1]
  },{
		name: '2020/8',
		data: [-0.2, -0.3, 0.4, 0.1, 0.3]
  },
        ],
        responsive: {
          rules: [
            {
              condition: {
                maxWidth: 500
              },
              chartOptions: {
                legend: {
                  layout: "horizontal",
                  align: "center",
                  verticalAlign: "bottom"
                }
              }
            }
          ]
        }
      }
    };
  },
  mounted() {},
  methods: {
    myCallback() {
      console.log("this is callback function");
    }
  }
};
</script>

<style>

.highcharts-credits{
display: none;
}
.highcharts-container {

  width: 500px;
  height: 300px;
  border: 1px solid #ddd;
  margin: auto;
  z-index: 100;
}
.highcharts-legend{
    display: none;
}
.highcharts-axis-title{
    display: none;
}
.highcharts-title{
    display: none;
}
</style>
