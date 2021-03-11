<template>
  <div class="box" id="box"></div>
</template>

<script>
import * as echarts from 'echarts';

export default {
  data() {
    return {
      chart: {},
      options: {},
    };
  },
  mounted() {
    this.chart = echarts.init(document.getElementById('box'))

    this.option = {
      color: ['red', 'green', 'yellow'],
      title: {
          text: 'ECharts 入门示例'
      },
      legend: {
        data: ['销量','收入']
      },
      tooltip: {},
      xAxis: {
          type: 'category',
          boundaryGap: true,
          data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
      },
      yAxis: {
        type: 'value'
      },
      series: [{
          name: '销量',
          type: 'line',
          stack: 'total',
          data: [5, 20, 36, 10, 10, 20]
      },{
          name: '收入',
          type: 'line',
          stack: 'total',
          data: [5, 20, 36, 10, 10, 20]
      }]
    };

    this.chart.setOption(this.option)

  }
}
</script>

<style lang="css" scoped>
#box {
  width: 600px;
  height: 400px;
  margin: 10px auto;
}
</style>
