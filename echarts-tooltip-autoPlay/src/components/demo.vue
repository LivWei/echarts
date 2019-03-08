<template>
  <div class="wrapper">
    <div class="bar" id="bar"></div>
  </div>
</template>

<script>
import tools from "./tools";
var echarts = require("echarts");
export default {
  components: {},
  props: {},
  data() {
    return {};
  },
  created() {},
  mounted() {
    this.drawBar();
  },
  watch: {},
  computed: {},
  methods: {
    drawBar() {
      // 基于准备好的dom，初始化echarts实例
      var myChart = echarts.init(document.getElementById("bar"));
      // 指定图表的配置项和数据
      var option = {
        title: {
          text: "ECharts 入门示例"
        },
        tooltip: {},
        legend: {
          data: ["销量"]
        },
        xAxis: {
          data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
        },
        yAxis: {},
        series: [
          {
            name: "销量",
            type: "bar",
            data: [5, 20, 36, 10, 10, 20]
          }
        ]
      };
      // 使用刚指定的配置项和数据显示图表。
      myChart.setOption(option);
      //使用轮播插件
      tools.autoHover(myChart, option, 17, 3000);
    }
  }
};
</script>
<style scoped>
.wrapper {
  height: 300px;
  width: 500px;
}
.bar {
  height: 100%;
  width: 100%;
}
</style>