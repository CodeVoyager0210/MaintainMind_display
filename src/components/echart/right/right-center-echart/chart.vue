<template>
  <div>
    <Echart
      :options="options"
      id="RightCenterEchart"
      height="255px"
      width="100%"
    ></Echart>
  </div>
</template>

<script>
export default {
  data() {
    return {
      options: {},
    }
  },
  props: {
    cdata: {
      type: Object,
      default: () => ({}),
    },
  },
  watch: {
    cdata: {
      handler(newData) {
        this.options = {
          backgroundColor: 'transparent',
          tooltip: {
            trigger: 'axis',
            axisPointer: {
              type: 'line'
            }
          },
          legend: {
            data: ['温度(°C)', '压力(kPa)', '振动(mm/s)'],
            top: 10,
            textStyle: {
              color: '#fff'
            }
          },
          grid: {
            top: '15%',
            left: '5%',
            right: '5%',
            bottom: '20%',
            // containLabel: true
          },
          xAxis: [
            {
              type: 'category',
              axisLine: {
                show: true,
                lineStyle: {
                  color: 'rgba(255, 255, 255, 0.3)'
                }
              },
              axisLabel: {
                color: '#fff',
                textStyle: {
                  fontSize: '12'
                },
              },
              splitLine: {
                show: false,
              },
              boundaryGap: false,
              data: newData.time,
            },
          ],

          yAxis: [
            {
              type: 'value',
              name: '数值',
              nameTextStyle: {
                color: '#fff',
                fontSize: 12
              },
              splitLine: {
                show: true,
                lineStyle: {
                  color: 'rgba(255,255,255,0.1)',
                },
              },
              axisLine: {
                show: true,
                lineStyle: {
                  color: 'rgba(255, 255, 255, 0.3)'
                }
              },
              axisLabel: {
                show: true,
                color: '#fff',
                fontSize: 12
              },
              axisTick: {
                show: false,
              },
            },
          ],
          series: [
            {
              name: '温度(°C)',
              type: 'line',
              smooth: true,
              showAllSymbol: true,
              symbol: 'circle',
              symbolSize: 8,
              lineStyle: {
                normal: {
                  color: '#ff7f50',
                  width: 3
                },
              },
              label: {
                show: false,
              },
              itemStyle: {
                color: '#ff7f50',
                borderColor: '#fff',
                borderWidth: 2,
              },
              tooltip: {
                show: true,
              },
              data: newData.temperature,
            },
            {
              name: '压力(kPa)',
              type: 'line',
              smooth: true,
              showAllSymbol: true,
              symbol: 'circle',
              symbolSize: 8,
              lineStyle: {
                normal: {
                  color: '#87ceeb',
                  width: 3
                },
              },
              label: {
                show: false,
              },
              itemStyle: {
                color: '#87ceeb',
                borderColor: '#fff',
                borderWidth: 2,
              },
              tooltip: {
                show: true,
              },
              data: newData.pressure,
            },
            {
              name: '振动(mm/s)',
              type: 'line',
              smooth: true,
              showAllSymbol: true,
              symbol: 'circle',
              symbolSize: 8,
              lineStyle: {
                normal: {
                  color: '#9370db',
                  width: 3
                },
              },
              label: {
                show: false,
              },
              itemStyle: {
                color: '#9370db',
                borderColor: '#fff',
                borderWidth: 2,
              },
              tooltip: {
                show: true,
              },
              data: newData.vibration,
            },
          ],
        }
      },
      immediate: true,
      deep: true,
    },
  },
}
</script>
