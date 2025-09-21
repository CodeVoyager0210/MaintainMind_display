<template>
  <div>
    <Echart
      :options="options"
      id="LeftCenterEchart"
      height="255px"
      width="100%"
    ></Echart>
  </div>
</template>

<script>
export default {
  props: {
    cdata: {
      type: Object,
      default: () => ({}),
    },
  },
  data() {
    return {
      options: {},
      // 定义颜色
      colorList: [
        '#00AAFF',
        '#A52A2A',
        '#FF752D',
        '#FFCF31',
        '#FF3129',
        '#006400',
        '#8B4513',
        '#FF8C00',
        '#FFB6C1',
        '#7B68EE',
        '#87CEFA',
        '#008000',
        '#D2B48C',
      ],
    }
  },

  created() {},
  methods: {},
  watch: {
    cdata: {
      handler(newData) {
        this.options = {
          backgroundColor: 'transparent',
          grid: {
            left: '3%',
            right: '4%',
            bottom: '3%',
            top: '15%',
            containLabel: true,
          },
          tooltip: {
            trigger: 'axis',
            axisPointer: {
              type: 'line',
              lineStyle: {
                color: '#4eaafd',
                type: 'dashed'
              }
            },
            formatter: function(params) {
              let result = params[0].name + '<br/>'
              params.forEach(item => {
                result += item.marker + item.seriesName + ': ' + item.value + ' 小时<br/>'
              })
              return result
            }
          },
          legend: {
            data: ['发动机 #001', '发动机 #002', '发动机 #003'],
            top: 0,
            textStyle: {
              color: '#fff'
            }
          },
          xAxis: {
            type: 'category',
            boundaryGap: false,
            data: newData.months,
            axisLine: {
              lineStyle: {
                color: 'rgba(255, 255, 255, 0.3)'
              }
            },
            axisLabel: {
              color: '#fff',
              fontSize: 12
            }
          },
          yAxis: {
            type: 'value',
            name: '剩余寿命 (小时)',
            nameTextStyle: {
              color: '#fff',
              fontSize: 12
            },
            axisLine: {
              lineStyle: {
                color: 'rgba(255, 255, 255, 0.3)'
              }
            },
            axisLabel: {
              color: '#fff',
              fontSize: 12
            },
            splitLine: {
              lineStyle: {
                color: 'rgba(255, 255, 255, 0.1)'
              }
            }
          },
          series: [
            {
              name: '发动机 #001',
              type: 'line',
              smooth: true,
              symbol: 'circle',
              symbolSize: 8,
              data: newData.engine1,
              lineStyle: {
                color: '#5470c6',
                width: 3
              },
              itemStyle: {
                color: '#5470c6',
                borderColor: '#fff',
                borderWidth: 2
              },
              areaStyle: {
                color: new this.$echarts.graphic.LinearGradient(0, 0, 0, 1, [
                  { offset: 0, color: 'rgba(84, 112, 198, 0.5)' },
                  { offset: 1, color: 'rgba(84, 112, 198, 0.1)' }
                ])
              }
            },
            {
              name: '发动机 #002',
              type: 'line',
              smooth: true,
              symbol: 'circle',
              symbolSize: 8,
              data: newData.engine2,
              lineStyle: {
                color: '#91cc75',
                width: 3
              },
              itemStyle: {
                color: '#91cc75',
                borderColor: '#fff',
                borderWidth: 2
              },
              areaStyle: {
                color: new this.$echarts.graphic.LinearGradient(0, 0, 0, 1, [
                  { offset: 0, color: 'rgba(145, 204, 117, 0.5)' },
                  { offset: 1, color: 'rgba(145, 204, 117, 0.1)' }
                ])
              }
            },
            {
              name: '发动机 #003',
              type: 'line',
              smooth: true,
              symbol: 'circle',
              symbolSize: 8,
              data: newData.engine3,
              lineStyle: {
                color: '#fac858',
                width: 3
              },
              itemStyle: {
                color: '#fac858',
                borderColor: '#fff',
                borderWidth: 2
              },
              areaStyle: {
                color: new this.$echarts.graphic.LinearGradient(0, 0, 0, 1, [
                  { offset: 0, color: 'rgba(250, 200, 88, 0.5)' },
                  { offset: 1, color: 'rgba(250, 200, 88, 0.1)' }
                ])
              }
            }
          ]
        }
      },
      immediate: true,
      deep: true,
    },
  },
}
</script>
