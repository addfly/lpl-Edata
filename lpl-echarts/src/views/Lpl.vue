<template>
  <div class="about">
    <h1>可视化测试</h1>
    <div class="t0" id="main"></div>
  </div>
</template>

<script>
// 引入 ECharts 主模块
var echarts = require("echarts/lib/echarts");
// 引入柱状图
require("echarts/lib/chart/bar");
require("echarts/lib/chart/pie");
// 引入提示框和标题组件
require("echarts/lib/component/tooltip");
require("echarts/lib/component/title");
require("echarts/lib/component/grid");

export default {
  mounted: function() {
    this.edata();
  },
  methods: {
    edata() {
      // 基于准备好的dom，初始化echarts实例
      var myChart = echarts.init(document.getElementById("main"));
      // 绘制图表
      myChart.setOption({
        title: {
          text: "LPL数据分析图"
        },
        tooltip: {},
        xAxis: {
          data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
        },
        grid: [
          {
            top: 100,
            left: 100,
            height: "40%",
            width: "50%"
          }
        ],
        yAxis: {},
        series: [
          {
            name: "销量",
            type: "bar",
            data: [5, 20, 36, 10, 10, 20]
          },
          {
            name: "占比",
            type: "pie",
            data: [
              { name: "xx", value: 3 },
              { name: "yy", value: 15 }
            ],
            center: [400, 400],
            radius: 50
          }
        ]
      });
    }
  }
};
</script>

<style lang="less" scoped>
.about {
  display: flex;
  flex-direction: column;
  .t0 {
    width: 800px;
    height: 500px;
  }
}
</style>
