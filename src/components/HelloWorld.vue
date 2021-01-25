<template>
  <div id="myChart" :style="{ width: '300px', height: '300px' }"></div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      type: ["啤酒", "饮料", "花生", "瓜子"],
    };
  },
  mounted() {
    this.drawLine();
  },
  methods: {
    drawLine() {
      var echarts = require("echarts");
      var myChart = echarts.init(document.getElementById("myChart"));
      myChart.setOption({
        title: {
          text: "ECharts 入门示例",
        },
        tooltip: {},
        xAxis: {
          data: this.type,
        },
        yAxis: {},
        series: [
          {
            name: "销量",
            type: "bar",
            data: [5, 20, 36, 10, 10, 20],
          },
        ],
      });
    },
  },
};
</script>

<style scoped lang="less">
</style>
