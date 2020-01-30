<template>
  <div>
    <!-- <div>{{a.msg}}</div> -->
    <div ref="chart" class="onechart"></div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Echart from "echarts";

export default Vue.extend({
  name: "BarDashboard",
  data() {
    return {
      a: {
        msg: "hello"
      },
      chart: {},
      b: []
    };
  },
  methods: {
    refreshChart() {
      let option = {
        title: {
          top: 30,
          left: "center",
          text: "日历热力图"
        },
        tooltip: {},
        visualMap: [
          {
            min: 0,
            max: 10000,
            type: "piecewise",
            orient: "horizontal",
            left: "center",
            top: 65,
            textStyle: {
              color: "#000"
            }
          }
        ],
        calendar: [
          {
            top: 120,
            left: 80,
            right: 80,
            cellSize: ["auto", 13],
            range: "2016",
            itemStyle: {
              borderWidth: 0.5
            },
            yearLabel: {
              formatter: "{start}",
              textStyle: {
                color: "#000"
              }
            }
          }
        ],
        series: [
          {
            type: "heatmap",
            coordinateSystem: "calendar",
            data: [
              ["2016-01-01", 10000],
              ["2016-01-05", 8000],
              ["2016-01-09", 3000],
              ["2016-01-12", 9000]
            ]
          }
        ]
      } as Echart.EChartOption;

      (this.chart as Echart.ECharts).setOption(option);
    }
  },
  mounted() {
    this.chart = Echart.init(this.$refs["chart"] as HTMLDivElement);
    this.refreshChart();
  }
});
</script>

<style lang="scss" scoped>
.onechart {
  height: 400px;
}
</style>
